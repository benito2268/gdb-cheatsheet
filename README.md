# CS354 GDB Cheatsheet
GDB is a program debugger for debugging executable files (usually compiled from C or C++). It works like most other debuggers, except instead of pressing buttons GDB uses commands.
This guide contians a few basic commands and tips on how to use GDB.

## Basics
GDB makes use of extra information the compiler can include in your executable file using the ```-g``` flag
A modified GCC compile command for 354:
```bash
gcc -Wall -m32 -std=gnu99 -g my_c_file -o my_prog
```

Load a program in GDB: 
```bash
gdb my_prog
```

GDB also has a text-based user interface (TUI). It shows your source code and the GDB command console side by side. You can enable it by typing:
```
layout src
```
in the GDB console. If you would like this to be the default run:
```bash
echo "layout src" >> ~/.gdbinit
```
from the terminal while SSH'd into a CSL machine.

## Locate a Segfault
With a program loaded in GDB type ```run```. You should see a message like ```Program recieved signal SIGSEGV, Segmentation fault. ... at my_file.c:2```
This will show you the line number the segfault happened on.
