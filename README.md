# CS354 GDB Cheatsheet
GDB is a program debugger for debugging executable files (usually compiled from C or C++). It works like most other debuggers, except instead of pressing buttons GDB uses commands.
This guide contians a few basic commands and tips on how to use GDB.

## Basics
GDB makes use of extra information the compiler can include in your executable file using the ```-g``` flag
A modified GCC compile command for 354:
<pre> ```bash 
  gcc -m32 -Wall -std=gnu99 my_file.c -g -o my_prog``` 
</pre>
Load a program in GDB: 
<pre> ```bash 
  gdb my_prog```
</pre>

## Locate a Segfault
With a program loaded in GDB type ```run```. You should see a message like ```Program recieved signal SIGSEGV, Segmentation fault. ... at my_file.c:2```
This will show you the line number the segfault happened on.
