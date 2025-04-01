# 8086 Assembly Code: Factorial Calculation

        MOV AX,0000      ; Clear AX register (AX will store the factorial result)
        MOV SI,3000      ; Load SI with the memory address containing the number
        MOV AL,[SI]      ; Load AL with the number from memory
        MOV CL, AL       ; Copy AL to CL (loop counter for multiplication)
        DEC CL           ; Decrement CL since factorial starts multiplication from (N-1)
    L1: MUL CL           ; Multiply AL (factorial result) by CL
        DEC CL           ; Decrement CL for next multiplication
        JNZ L1           ; Loop until CL becomes zero
        INT 03           ; Breakpoint for debugging (pauses execution for inspection)

Note :
 MUL CL multiplies AL by CL, and the result is stored in AX.
 If the number is too large, the result might overflow.
 INT 03 is used here for debugging.
