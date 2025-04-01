# LOGICAL OR OPERATION

    MOV AX,0000    ; Initialize AX register with 0
    MOV AX,0025    ; Load AX with the value 0x0025
    MOV BX,0054    ; Load BX with the value 0x0054
    OR AX,BX       ; Perform bitwise OR operation between AX and BX, result stored in AX
    INT 03         ; Trigger a software breakpoint interrupt (used for debugging)
