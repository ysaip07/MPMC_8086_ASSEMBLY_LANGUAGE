# 8086 Assembly Code:STEPPER MOTOR ROTATION IN CLOCK-WISE DIRECTION

    MOV AL,80       ; Load AL with 80H (possibly an initial value for output)
    MOV DX,0FFE6H   ; Load DX with port address 0FFE6H
    OUT DX,AL       ; Output AL to the port (some hardware interaction)   
    MOV BX,1770H    ; Load BX with 1770H (used as a counter)
    MOV AL,33H      ; Load AL with 33H (initial pattern for output)
    MOV DX,0FFEOH   ; Load DX with another port address
BACK:OUT DX,AL       ; Output AL to the port
     MOV CX,1262H    ; Load CX with delay counter
SELF:LOOP SELF       ; Delay loop (CX decrements until zero)
    ROR AL,1        ; Rotate AL right by 1 bit (shifting the output pattern)
    DEC BX          ; Decrease BX counter
    JNZ BACK        ; If BX is not zero, repeat the loop
    INT 03              ; Interrupt 3 (Breakpoint for debugging)
