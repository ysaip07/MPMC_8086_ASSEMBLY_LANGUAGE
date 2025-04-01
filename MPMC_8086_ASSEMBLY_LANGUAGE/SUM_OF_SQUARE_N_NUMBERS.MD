# 8086 Assembly Code: Sum of squares of N Integers

        MOV AX,0000
        MOV CX,#N    //N INPUTS
        MOV SI,4000
        MOV BX,0000
    L1: MOV AL,[SI]
        MUL AL
        ADD BX,AX
        INC SI
        DEC CX
        JNZ L1
        INT 03
-->