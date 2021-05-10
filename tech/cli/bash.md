# Bash

## Tips

- `help <builtin>` for builtin commands. Eg: `help test`, `help set`
- `tail -f /dev/null --pid=<pid>` - wait for process to exit (from any shell, while `wait` only work for child)
- `-v/-x` - verbose / trace
- `-l/-i` - login / interactive

## Dash

- Bash vs Dash: https://www.jpsdomain.org/public/2008-JP_bash_vs_dash.pdf
- Test (`[[` vs `[`/`test`) Differences: http://mywiki.wooledge.org/BashFAQ/031

### What Doesn't Work

- `[[` - tests and all related things like regex, operators (`==`, `=~`, `&&`, `||`)
- `All pipe redirect with & (eg: &>)` - `&` is only interpreted as background job
- `for ((i=0; i > 10; i++))` - Arithmetic for
- `$((i=0))` - Arithmetic works with `$(($i++))` as `$var`
- `function foo()` - Works without prefix word `function`
- `source` function. Use `.`

## Bash History

`!$` - last argument from previous command
`!^` - first argument (after the program/built-in/script) from previous command
`!!` - previous command (often pronounced "bang bang")
`!n` - command number n from history
`!pattern` - most recent command matching pattern
`!!:s/find/replace` | `^find^replace` - last command, substitute find with replace

## References

- Read: https://www.computerhope.com/unix/bash/read.htm
- Variables and Parameter Expansion: https://wiki-dev.bash-hackers.org/syntax/pe
- IO Redirection: https://catonmat.net/bash-one-liners-explained-part-three
- Process Substitutions: https://www.linuxjournal.com/content/shell-process-redirection
- Exec: https://www.computerhope.com/unix/bash/exec.htm
- Other Shells: http://hyperpolyglot.org/unix-shells
- getopt(s): https://dustymabe.com/2013/05/17/easy-getopt-for-a-bash-script/
- Read Into Array: https://kaijento.github.io/2017/03/19/bash-read-file-into-array/
- Bash history: https://stackoverflow.com/a/36654936