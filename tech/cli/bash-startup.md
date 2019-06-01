# Bash Startup

## Debian

### Login

- __/etc/profile__:
  - Interactive: `/etc/bash.bashrc`, `/etc/profile.d/*.sh`
  - Non-interactive: `/etc/profile.d/*.sh`
- __.profile__: .bashrc, self

### Non-login

- __/etc/bash.bashrc__:
  - Non-interactive: return
  - Interactive: self
- __.bashrc__:
  - Non-interactive: return
  - Interactive: self

### Notes

- bash compiled with `-DSYS_BASHRC`
  [ `/etc/bash.bashrc` is read before `~/.bashrc` for interactive non-login shells ]
- default profile.d implementation sets up bash_completion, vte, locale fixes, input method,
  xdg dirs for desktop session, snap etc.

## Fedora

### Login

- __/etc/profile__: self, `/etc/profile.d/*.sh`, `/etc/bashrc`
- __.profile__: `.bashrc`, self

### Non-login

- __.bashrc__: `/etc/bashrc`
- __/etc/bashrc__: `/etc/profile.d/*.sh` (non-login-only)

### Notes

- __/etc/bashrc__: double-sourcing protected
- default profile.d implementation sets up colors, bash_completion, vte, sh.local, etc
  and does most sane defaults, since it's executed in all contexts.
