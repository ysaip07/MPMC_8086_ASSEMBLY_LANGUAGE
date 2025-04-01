<!-- 
        MOV AX,0000
        MOV SI,4000
        MOV BX,5000
        MOV DI,6000
        MOV CL,08
    L1: MOV AL,[SI]
        ADD AL,[BX]
        MOV [DI],AL
        INC SI
        INC BX
        INC DI
        DEC CL
        JNE L1
        INT 03
-->