# BASIC SUBTRACTION OPERATION

    MOV AX, 0000    ; Reset AX (clearing any previous value)   
    MOV AX, 0025H   ; Load AX with 0025H (37 in decimal)
    MOV BX, 0054H   ; Load BX with 0054H (84 in decimal)
    SUB AX, BX      ; Subtract BX from AX: AX = AX - BX  
    INT 03          ; Breakpoint interrupt (used for debugging)
