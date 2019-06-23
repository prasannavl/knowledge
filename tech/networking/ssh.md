# ssh

## Common Use Cases

### `ssh-copy-id`

`ssh-copy-id user@host`
`ssh-copy-id -i ~/.ssh/mykey user@host`

- Logs into the remote using currently existing auth
- Copies keys to from current host to remote using correct permissions
- Adds it to  `authorized_keys` file

### `ssh-agent` and `ssh-add`

- [TODO]

## Port Forwarding

- Port `0` is usually used for random runtime assignment.

### Server Config

Config | Options | Description
--- | --- | ---
AllowTcpForwarding | `yes` or all, no, local, remote | Control TCP forwarding
AllowStreamLocalForwarding | Same as above | Control UNIX Domain Sockets forwarding 
GatewayPorts | `no`, yes, clientspecified | Useful for remote forwarding. By default, sshd(8) binds remote port forwardings to the loopback address only <br/><br/>no - Don't allow other IPs to connect <br/>yes - Allow any IPs to connect to forwarded port <br/>clientspecified - Allows only provided IPs to connect

### Local

![Illustration](https://i.stack.imgur.com/a28N8.png)


`ssh -L [lface:]lport:target:rport ssh-remote`

Connect to `target:rport` through `ssh-remote`, and make it available locally on `lface:lport`

**Examples:**

- `ssh -L 5499:localhost:5432 remote`
    - The local port of `5499` is forwarded to `remote:5499`.
- `ssh -L 5499:internal-db:5432 bastion`
    - The local port of `5499` is forwarded to `internal-db:5432`, through `bastion`.

Above is equivalent to: `ssh -L *:5499:internal-db:5432 bastion`, listening on all interfaces on the client allowing any interface on the client to connect.

For client-side local only access: `ssh -L 127.0.0.1:5499:internal-db:5432 bastion`

SSH Client Config:
- `LocalForward` - forward option without specifying on the command line.

### Remote

![Illustration](https://i.stack.imgur.com/4iK3b.png)


`ssh -R [in-ip:]in-port:target:tport ssh-remote`

Connect to `ssh-remote` on port `in-port` (from `in-ip` only) to access `target:tport`

> By default, sshd(8) binds remote port forwardings to the loopback address. This prevents other remote hosts from connecting to forwarded ports. `GatewayPorts` can be used to specify that sshd should allow remote port forwardings to bind to non-loopback addresses, thus allowing other hosts to connect.

**Examples:**

- `ssh -R 5000:localhost:8000 remote`
    - The remote port of `5000` on `remote` is forwarded to `localhost:8000` (`client:8000`)

- `ssh -R 5000:client-side-host:8000 remote`
    - The remote port of `5000` on `remote` is forwarded to `client-side-host:8000`.

### Dynamic (SOCKS5 Proxy)

`ssh -D [lface:lport] remote`

Forward everything on `lface:lport` through remote to their destination and back

**Examples:**

- `ssh -D 1080 remote`
    - Use `1080` as local port and proxy through `remote`
- `ssh -CNnT -D 1080 remote`
    - Same as above, but execute it silently without a shell, with no command, stdin from `/dev/null` and with compression

## Common Options

Option | Description 
--- | ---
-f | Fork to background
-C | Enable compression
-N | No commands to be executed. Useful when only port forwarding
-n | Forward `stdin` from `/dev/null`. Useful when ssh is in background with `-f`, specifically when using X forwarding.
-T | Disable pseudo-terminal allocation
-X | X11 forwarding
-Y | Trusted X11 forwarding 
-q | Quiet mode


## References

- https://unix.stackexchange.com/questions/115897/whats-ssh-port-forwarding-and-whats-the-difference-between-ssh-local-and-remot
- https://help.ubuntu.com/community/SSH/OpenSSH/PortForwarding
- https://zaiste.net/ssh_port_forwarding/
