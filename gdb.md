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

- `break *[function]` - set breakpoint at the start of function
- `run [args]` - duh?
- `info registers` - get register state values (infos)
- `si` - step +one instruction
- `ni` - step +one through everything not only calls
- `set $[instruction]=[value]` - set/change instruction (eg: `set $eax=0`) [with `info registers`]

---