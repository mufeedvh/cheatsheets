# `radare2` cheatsheet

like some radare2 commands and stuff bro.

## starting

```
$ r2 file
 -- never gonna give you up.
[0xaddress]> aaa
[x0address]> afl
...
start doing stuff
```

## commands

- `i` - file overview/info
- `aaa` - analyse
- `afl` - analyse functions list - lists all the functions
- `s [0xaddress/function_name]` - seek command, to move/jump around to functions and stuff
- `p?` - print commands
- `pd?` - disassemble opcodes
- `pdf` || `pdf @[0xaddress/function_name]` - disassemble function
- `iz` - print strings
- `iz~[string]` - search for a _string_ (eg: `iz~password`)
- `? 0xaddress` - calculate/get info of address values (read variables and stuff)
- `CC [comment] @0xaddress` - add/remove comments
- `ax?` - available "reference analyse" (`ref/xref`) commands
- `axt [0xaddress]` - find data/code references to an `address`
- `pd [lines]` || `pd [lines]@[0xaddress]` - print `X` lines of disassembly

# tips

```asm
push eax
push dword [local_Xh]
call sym.imp.strcmp
```

arguments to a function call can be seen on top of it as variables `push`ed to stack, get the address of it or refer to the local variables on top to seek that.

- `pd 10@0xaddress` - prints 10 lines from that address, epic when looking at certain part of the code

- `? 0xaddress` - see the value of an address/variable:

```asm
...
... mov dword [local_41eh] 0xaddress
...
[0xaddress]> ? 0xaddress
<info and values of that address/variable>
```

- `$$` in commands denotes where we are standing

- check for cross references (`ref/xref`s) on empty address values because they might be populated later on

- feeling _fuck this shit im out?_ use `cutter`

## calculation with `?` command

`? 0x6+9` -> `0x14`

**function name example:** `sym.main`
**in a command:** `pdf @sym.main`
