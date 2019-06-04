# ssh

## Common Use Cases

## `ssh-copy-id`

`ssh-copy-id user@host`
`ssh-copy-id -i ~/.ssh/mykey user@host`

- Logs into the remote using currently existing auth
- Copies keys to from current host to remote using correct permissions
- Adds it to  `authorized_keys` file

## `ssh-agent` and `ssh-add`

