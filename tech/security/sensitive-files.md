# Sensitive files

- Files that are sensitive, normally found in a developer's desktop.
- These are not system config files that when misconfigured could be exploited - there's plenty
of that. This document only covers files **that directly contain sensitive user information**.

## User files

### `$HOME` paths

**Windows:** `%UserProfile%`, eg: `C:\Users\pvl`
**Linux:** `/home/<user>`, eg: `/home/pvl`

Path | Package | Notes
---  | --- | ---
.gnupg | gnupg | keys and config
.ssh | ssh | keys and config
.npmrc | npm | Auth token
.cargo/credentials | rustup / cargo | Auth token

### `config` paths

**Windows:** 
    - `%AppData%`, eg: `C:\Users\pvl\AppData\Roaming`
    - `%LocalAppData%`, eg: `C:\Users\pvl\AppData\Local`

**Linux:** `$XDG_CONFIG_HOME`, eg: `/home/pvl/.config`

Path | Package | Notes
---  | --- | ---
Code/User/settings.json | vscode | Possible external tokens
Code/User/syncLocalSettings.json | vscode | Sync token

### `data` paths

**Windows:** 
    - `%AppData%`, eg: `C:\Users\pvl\AppData\Roaming`
    - `%LocalAppData%`, eg: `C:\Users\pvl\AppData\Local`

**Linux:** `$XDG_DATA_HOME`, eg: `/home/pvl/.local/share`

Path | Package | Notes
---  | --- | ---
\- | - | -

## System files

### Linux

Path | Package | Notes
---  | --- | ---
/etc/shadow | system | Hashed system passwords
/etc/NetworkManager/system-connections/ | network-manager | Network and Wi-Fi credentials
