# `gdb` cheatsheet

like some gdb commands and stuff bro.

## starting

```
$ gdb [filename]
...
(gdb) set disassembly-flavor intel
(gdb) disassemble main
...
...
...
```

## commands

- `break *[address]` - set breakpoint at the start of the function
- `break [function.Function]` - set breakpoint at the start of the function (eg: `break strings.Compare`)
- `run [args]` - duh?
- `info registers` - get register state values (infos)
- `s` - step one
- `si` - step +one instruction
- `ni` - step +one through everything not only calls
- `set $[instruction]=[value]` - set/change instruction (eg: `set $eax=0`) [with `info registers`]
- `info args` - see if any arguments are passed to calls

---
