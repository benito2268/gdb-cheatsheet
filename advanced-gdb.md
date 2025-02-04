## Passing Command-line args
With a file loaded in GDB, use ```run \<args\>``` to pass CLAs

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

