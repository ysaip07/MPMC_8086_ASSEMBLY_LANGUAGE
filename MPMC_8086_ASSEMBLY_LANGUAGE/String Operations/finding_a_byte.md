# 8086 Assembly Code: Finding a byte in given string

MOV SI,4000         ;Load SI with the starting address of the first data block (source)
MOV DI,5000         ; Load DI with the starting address of the second data block (destination)
MOV CX,0006         ; Load CX with the number of bytes to compare (6 bytes)
CLD                 ; CLD (Clear Direction Flag) makes SI and DI increment after each comparison
CMPSB               ; Compare byte at [SI] with byte at [DI], SI and DI increment automatically
REPNE               ; Repeat CMPSB until CX=0 or bytes match (ZF=1)
INT 03              ; Interrupt 3 (Breakpoint for debugging)
