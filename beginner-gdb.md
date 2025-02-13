# CS354 GDB Cheatsheet
GDB is a program debugger for debugging executable files (usually compiled from C or C++). It works like most other debuggers, except instead of pressing buttons GDB uses commands.
This guide contians a few basic commands and tips on how to use GDB.

## Basics
GDB makes use of extra information the compiler can include in your executable file using the ```-g``` flag.

Compile your C code with:
```bash
gcc -Wall -m32 -std=gnu99 -g my_c_file -o my_prog
```

Load the program in GDB: 
```bash
gdb my_prog
```

GDB also has a text-based user interface (TUI). It shows your source code and the GDB command console side by side. To enable it, type this (in the GDB console!):
```
layout src
```

If you would like this to be the default every time you run GDB type this in the linux terminal of a CSL machine:
```bash
echo "layout src" >> ~/.gdbinit
```

## Locate a Segfault
With a program loaded in GDB type ```run```. You should see a message like ```Program recieved signal SIGSEGV, Segmentation fault. ... at my_file.c:2```
This will show you the line number the segfault happened on.


## Common GDB commands
Most GDB commands are simmilar to buttons you may have seen in other debuggers. Most also have single-letter shorthand aliases, which are listen below.

| Command | Shorthand | Function |
----------|-----------|-----------
| run     | r         | run the currently loaded program |
| print \<c-expr\> | p \<c-expr\> | print the value of a variable, result of a calculation, or any C expression |
| break \<line\> | b \<line\> | set a break point at a line |
| break \<function-name\> | b \<function-name\> | set a breakpoint at the beginning of a function |
| step | s | advance to the next line while paused (step into) |
| next | n | advance to the next line while paused - skipping function calls (step over) |
| continue | c | resume the program after a breakpoint |
| finish |  | resume the program, run until the end of the current function, then pause again |
| quit | q | exit GDB |

## ```print``` Examples
* ```print my_int```
* ```print my_int + 5 / 2 + 3```
* ``` print foo() ```
* ``` print *my_ptr```
* ``` print my_list[5] ``` 
