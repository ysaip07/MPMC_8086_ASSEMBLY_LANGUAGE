# BASIC ADDITION OPERATION

    MOV AX,0000   ; Resetting the accumulator (AX register) to 0
    MOV AX,0025H   ; Load AX with the value 0025H
    MOV BX,0054H   ; Load BX with the value 0054H
    ADD AX,BX     ; Add BX to AX , result stored in AX
    INT 03        ; Trigger software breakpoint (used for debugging)
