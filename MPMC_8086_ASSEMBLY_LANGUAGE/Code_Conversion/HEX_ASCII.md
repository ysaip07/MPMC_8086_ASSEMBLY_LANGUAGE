<!--
        MOV SI,2000
        MOV DI,3000
        MOV CX,0003
    L2: MOV AL,[SI]
        CMPB AL,0A
        JC L1
        ADD AL,07
    L1: OR AL,30
        MOV [DI],AL
        INC SI
        INC DI
        DEC CX
        JNZ L2
        INT 03

-->