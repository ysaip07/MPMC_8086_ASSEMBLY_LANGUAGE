# MPMC_8086_ASSEMBLY_LANGUAGE

# 8086 Microcontroller

8086 has a set of general-purpose registers and special-purpose registers:

1️. General-Purpose Registers
These can be used for arithmetic, data transfer, and logic operations:

Registers
AX (Accumulator)    ;Used for arithmetic & I/O operations
BX (Base)           ;Base register for addressing
CX (Counter)        ;Used for loops and shifts
DX (Data)           ;Used for I/O operations & multiplication/division

2️.Segment Registers
8086 uses segmentation to access memory:

Registers
CS (Code Segment)   ;Holds code (instructions)
DS (Data Segment)   ;Holds variables & data
SS (Stack Segment)  ;Holds the stack
ES (Extra Segment)  ;Used for memory operations

3️.Pointer & Index Registers

Registers
SP (Stack Pointer)      ;Points to the top of the stack
BP (Base Pointer)       ;Used for stack frame addressing
SI (Source Index)       ;Used in string operations
DI (Destination Index)  ;Used in string operations

The primary reason for using INT 03 in 8086 assembly is debugging. Here’s why it's commonly used:

1️. Breakpoint for Debugging
INT 03 is a software breakpoint used by debuggers.

When executed, it pauses the program, allowing the user to inspect registers, memory, and execution flow.

This is useful for checking the results of CMPSB and REPNE operations before continuing execution.

2️. Single-Byte Instruction (CC Opcode)
Unlike other interrupts that require two bytes (e.g., INT 21H is CD 21 in machine code), INT 03 is encoded as just one byte (CC).

This makes it easier to insert dynamically in memory for debugging purposes.

3️. Does Not Require Additional Setup
Unlike INT 21H, which requires loading a function number into AH (e.g., MOV AH, 4CH for termination), INT 03 works directly without any additional setup.
