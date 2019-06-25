# CLI Common Cases

## Global Conventions

- `-v` - verbose
- `-h` - `human readable` or help when human readable doesn't apply
- `--help` - help

## `cp, mv, install` etc

Single SOURCE:

`cp [OPTION]... [-T] SOURCE DEST`

- `-T, --no-target-directory` - Treat DEST as a normal file

Multiple SOURCEs:

`cp [OPTION]... SOURCE... DIRECTORY`

`cp [OPTION]... -t DIRECTORY SOURCE...`

- `-t, --target-directory=DIRECTORY` - All SOURCE arguments into DIRECTORY

## `cp, mv` Common Options

- `-i` - interactive
- `-b, --backup=[CONTROL] | -S/--suffix=[~]` - backup
- `--strip-trailing-slashes` - remove any trailing slashes from each SOURCE argument; useful in scripts.

Conflict resolution:

- `-n` - no clobber
- `-f` - force clobber [remove dest first]
- `-u` - update only when source is newer

## cp

Common cases:

- `cp -a` - Preserve security context, xattrs, etc - Also implies `dR` - no-deference links
- `cp -R/-r` - Recursive (`R` is only for parity with `ls -R` where `r` is reverse sort)
- `cp --parents ./<src> <dest>/` - To copy current [dot-prefixed] dir tree into dest
- `cp --parents <src> <dest>` - To copy absolute path from root tree into dest
- `cp -R src/. dest` - Copy all the contents of the src into dest. Note the `dot` after `src`

Useful options:

- `-L` - override no-deference to always follow sym links
- `-x` - stay inside one fs
- `-s` - sym link instead of copy

Default preserves: `timestamp, mode, owner`
