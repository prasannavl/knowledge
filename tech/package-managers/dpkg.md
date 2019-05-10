# `dpkg` Package Management

## Install / Uninstall

Cmd | Option | Description
-- | -- | --
`dpkg -i file.deb` | `--install` | Install deb
`dpkg -P pkg_name` | `--purge` | Remove package
`dpkg -r pkg_name` | `--remove` | Remove but leave configs

## Extract / Unpack

Cmd | Option | Description
-- | -- | --
`dpkg -x file.deb [target_dir]` | `--extract` | Extract files from a .deb file
`dpkg --unpack file.deb` | | Unpack .deb to install location

## State

Cmd | Option | Description
-- | -- | --
`dpkg -s pkg_name` | `--status` | Package status
`dpkg --get-selections` | | Get package states
`dpkg --set-selections` | | Set package states

## Inspect

Cmd | Option | Description
-- | -- | --
`dpkg -l [pkg_pattern]` | `--list` | List installed packages
`dpkg -L pkg_name` | `--listfiles` | List all files in an installed package
`dpkg -c file.deb` | `--contents` | List all files from a .deb file
`dpkg -S file_pattern` | `--search` | Search for installed package(s) with file name pattern

## Configure

Cmd | Description
-- | --
`dpkg --configure pkg_name [-a\|--pending]` | Run package config
`dpkg --triggers-only pkg_name [-a\|--pending]` | Run package triggers only
