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

## References

- Read: https://www.computerhope.com/unix/bash/read.htm
- IO Redirections: https://catonmat.net/bash-one-liners-explained-part-three
- Process Substitutions: https://www.linuxjournal.com/content/shell-process-redirection
- Exec: https://www.computerhope.com/unix/bash/exec.htm
- Other Shells: http://hyperpolyglot.org/unix-shells