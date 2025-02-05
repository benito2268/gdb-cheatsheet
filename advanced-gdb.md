## Passing Command-line args
With a file loaded in GDB, use ```run <args>``` to pass CLAs. For example ```run hello 5 world```

## The ```x/nfu``` Command
One of the most powerful (and confusing :P) commands in GDB is ```x/nfu <address>```, which allows you to inspect the contents of memory at a given address.
When typing the command the ```nfu``` part is replaced with 3 parameters summarized below.
* n (number) - the number of things to print - any integer value
* f (format) - the numeric base to print in - 'x' for hexadecimal, 'd' for decimal, 'u' for unsigned, 't' for binary.
* u (unit) - what is the "thing" we mentioned above? - 'b' for byte (8 bits), 'h' for halfword (16 bits), 'w' for word (32 bits), 'g' for giantword (64 bits)

The following example would print 4 bytes, in hexadeciaml, starting at memory address 0x1234, when typed in the GDB console.
```x/4xb 0x1234```

## Watchpoints
A watchpoint will cause the debugger to pause when the value of the variable you're watching changes
To set a watchpoint type:
```
watch <variable-or-expression>
```

#### Watching a memory address
```
watch *0x1234
````

## Debugging Assembly (code compiled without ```-g```)
* Use ```layout asm``` (similar to layout src but displays the whole file in assembly)
* Use ```stepi``` or ```si``` to step to the next instruction (rather than line)
* Break on a specific address by using ```break *<address>```
* Use ```info registers``` to view the contents of each CPU register

