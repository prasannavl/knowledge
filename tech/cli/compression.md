# Compression

## tar

Command | Description
--- | ---
`tar cf <file.tar> file1 file2 dir1` | Compress into file.tar
`tar xf <file.tar>` | Extract file.tar into cwd
`tar xvzf <file>` | v - verbose; z - gzip
`tar xvjf <file>` | v - verbose; j - bzip

### Notes

- Compression creates new files, while extraction will overwrite any existing by default. 
- Tar stores file sequentially without any index metadata.
- ^ Listing requiring scanning all blocks, while appending is easy. 
- ^ Deleting a single file requires rewriting the whole archive.

## gzip / bzip2

Most gzip and bzip2 options for common cases remain the same - They are interchangeable. 

Command | Description
--- | ---
`gzip file` | Compress file to file.gz and delete file
`gzip -9 file` | ^ Use compression level 9
`gunzip file.gz` / `gzip -d file.gz` | Deflate file.gz to file and delete file.gz
`-c` | To stdout, for piping (doesn't touch original, -k implied)
`-k` | Keep original file
`-f` | Force overwrite

## Notes 

- Deletes original file by default, on both compress and deflate.