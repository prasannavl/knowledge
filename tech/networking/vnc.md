# VNC

## Common Options

### TigerVNC

- `vncserver -list` - List current servers
- `vncserver -kill` - Kill servers
- `vncserver -localhost no` - List on non localhost ifaces
- `x0vncserver -passwordfile ~/.vnc/passwd -display :0` - Existing display

### X11 VNC 

- `x11vnc -display :0` - Listen on existing display
