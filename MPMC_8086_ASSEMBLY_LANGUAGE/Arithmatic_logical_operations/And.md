# LOGICAL AND OPERATION

    MOV AX, 0000    ; Resetting the accumulator (AX = 0)
    
    MOV AX, 0025h   ; Load AX with the hexadecimal value 0025h (37 in decimal)
    MOV BX, 0054h   ; Load BX with the hexadecimal value 0054h (84 in decimal)
    
    AND AX, BX      ; Perform a bitwise AND operation between AX and BX
                    ; 0025h =  0010 0101 (binary)
                    ; 0054h =  0101 0100 (binary)
                    ; ---------------------
                    ; Result  = 0000 0100 (binary) = 0004h (decimal 4)
    
    INT 03          ; Trigger a breakpoint interrupt (used for debugging)
