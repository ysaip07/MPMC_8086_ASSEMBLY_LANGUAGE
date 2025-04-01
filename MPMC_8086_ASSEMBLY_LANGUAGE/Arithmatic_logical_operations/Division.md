# DIVISION OPERATION

    MOV AX,0000  //Resetting Accumulator
    MOV AX,0025
    MOV BL,05
    DIV BL
    INT 03
