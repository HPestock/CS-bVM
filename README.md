# CS-bVM
Chris' Stack-based VM (That's me)

This project was created using the p5.js library found at p5js.org -- I had nothing to do with the creation or development of p5.js. 
This repository includes the github demo that can be found at hpestock.github.io and has a small change to the method of reading asm code. 

Instruction set: <br>
0x0000 | NOP, <br>
0x0001 | PUSH, (NUMBER), - push NUMBER to stack <br>
0x0002 | PUSHM, (LOCATION), - push memory[LOCATION] to stack <br>
0x0003 | POP, (STACK LOCATION), - remove {pop} stack value STACK LOCATION (0 is top, 1 is top -1, etc...) <br>
0x0004 | CLRST, - clear stack <br>
0x0005 | MSM, (STACK NUMBER), (MEMORY LOCATION), -  copy value from stack[STACK NUMBER] (0 is top) to memory[MEMORY LOCATION] <br>
0x0006 | ADDT, - add top two numbers on stack <br>
0x0007 | SUB, - subtract top two numbers on stack <br>
0x0008 | MULT, - multiply top two numbers on stack <br>
0x0009 | DIV, - divide top two numbers on stack <br>
0x000a | MOD, - modulo top two numbers on stack <br>
0x000b | DRAW, - draw at (X,Y,R,G,B,Scale) stack[SP-5], stack[SP-4], etc... <br>
0x000c | JMP, (MEMORY LOCATION), - jump to MEMORY LOCATION (insts start at 600 and end at 999 but can go from 0 to 999, will be stopped after 1 inst after 999) <br>
0x000d | JSR, (MEMORY LOCATION), - JMP and set PCRET to (PC + 2) <br>
0x000e | RTS, - return from subroutine (JSR) and set PC to PCRET <br>
0x000f | CMPEQ, - set flag_cmp to 1 if stack[SP-1] == stack[SP] otherwise set flag_cmp to 0 <br>
0x0010 | CMPNEQ, - set flag_cmp to 1 if stack[SP-1] != stack[SP] otherwise set flag_cmp to 0 <br>
0x0011 | CMPGT, - set flag_cmp to 1 if stack[SP-1] > stack[SP] otherwise set flag_cmp to 0 <br>
0x0012 | CMPGE, - set flag_cmp to 1 if stack[SP-1] >= stack[SP] otherwise set flag_cmp to 0 <br>
0x0013 | CMPLT, - set flag_cmp to 1 if stack[SP-1] < stack[SP] otherwise set flag_cmp to 0 <br>
0x0014 | CMPLE, - set flag_cmp to 1 if stack[SP-1] <= stack[SP] otherwise set flag_cmp to 0 <br>
0x0015 | BIP, (MEMORY LOCATION), - branch to MEMORY LOCATION if flag_cmp is set to 1 <br>
0xffff | HALT, - set PC to 1000 <br>

CS-bVM (c) Christian Pestock 2020
