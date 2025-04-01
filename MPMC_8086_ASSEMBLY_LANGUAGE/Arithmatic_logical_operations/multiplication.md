# MULTIPICATION

    MOV AX,0000    ; Resetting Accumulator (AX)
    MOV AX,0025    ; Load AX with the value 0x0025
    MOV BX,0054    ; Load BX with the value 0x0054
    MUL BX         ; Multiply AX by BX (Result stored in DX:AX)
    INT 03         ; Trigger a software breakpoint interrupt (used for debugging)
