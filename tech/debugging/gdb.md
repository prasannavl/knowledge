# gdb

## Startup Routine

Binary:

- `gdb binary` / `gdb --args <args...>`
- `set args <args...>` - set args if needed
- `break <where>` - set breakpoints as necessary
- `r` - run

Core dumps:

- `gdb binary core-dump`

## Paths

- `directory <dir` / `dir <dir>`
    - Add dir to the front of the _source_ path
    - Without dir argument resets path to `$cdir:$cwd`
- `set directories <path-list>`
    - Set the _source_ path to path-list. `$cdir:$cwd` added if missing.
- `set substitute-path <from> <to>`
    - Substitution rule for finding _source_ files
    - With arguments, all substitution rules are deleted.
- `set solib-search-path <dir>`
    - Specifies directories where GDB will search for shared libraries with symbols. Very useful when debugging with gdbserver.

## Symbols

- `set debug-file-directory <dir>`
    - Symbols files are loaded from dir as long as the binary supports debug-link and
        provides the names.
- `add-symbol-file filename address`
    - Parameter address is the address for `.text` section.
    - Can be retrieved with:
        `readelf -WS <filename> | grep .text | awk '{ print "0x"$5 }'`

## Quick Debug

- `bt` - backtrace: show stack functions and args
- `info` frame - show stack start/end/args/locals pointers
- `x/100x $sp` - show stack memory

## Resources

- https://blogs.oracle.com/linux/8-gdb-tricks-you-should-know-v2
- https://reverseengineering.stackexchange.com/questions/1935/how-to-handle-stripped-binaries-with-gdb-no-source-no-symbols-and-gdb-only-sho
- https://darkdust.net/files/GDB%20Cheat%20Sheet.pdf