# specifications
Specifications for the smøken-cpu.

## principles
The architecture is designed to move certain aspects of concurrency away from the software space and introduce hardware level concurrency and a possibility to add instruction handlers to decrease the possible effects of bottlenecks.

## intent
This repository will contain the specifications for the smøken computer, which is aimed to be an educational microcomputer project that implements some unorthodox features in its architecture. These specifications are meant to be independent of the implementation's word size.

## purpose
The contents of this repository will hopefully be used to implement a fully working microcomputer at the [REDACTED] hackerspace.

## instruction handling
Every instruction handler has the following special registers:
+ tid register, contains the (hardware)thread id
+ instruction pointer, contains adress (inside the processes current instruction page) to fetch the next instrucion from
+ ? any more ?

Instruction handling follows the following cycle
1. Every instruction handler tries to fetch its next instruction from the adress specified in its instruction pointer, inside its current instruction page. All instruciton handlers that fail to do this (due to memory locks or similar errors) do not continue in the instruction handling sequence.
2. Every instruction handler tries check if all of its operands can be accessed or if they are memory-locked. Instruction handlers that are blocked in this way will not continue in the handling sequence.
3. The "hardware scheduling circuit" the assigns the available ALU-resources to the instrucion handlers with the following priority :
  * oldest instrucions (postponed in earlier cycles) come first
  * if multiple instruction handlers query the same resources at the same time, the instruction handlers with lower tid's get served first
4. the ALU carries out the instructions.
