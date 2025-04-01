# 8086 Assembly Code:STEPPER MOTOR ROTATION IN ANTI CLOCK-WISE DIRECTION

    MOV AL,80H       ; Load AL with 80H (possibly an initial output pattern)
    MOV DX,0FFE6H    ; Load DX with port address 0FFE6H
    OUT DX,AL        ; Send AL data to the port (hardware control)
    MOV BX,1770H     ; Load BX with a countdown value (used for repetition)
    MOV AL,33H       ; Load AL with 33H (initial output data)
    MOV DX,0FFEOH    ; Load DX with another I/O port address
BACK:OUT DX,AL        ; Output AL to port (sending data)
    MOV CX,1262H     ; Load CX with a delay counter
SELF:LOOP SELF        ; Delay loop (CX decrements until it reaches zero)
     ROL AL,1         ; Rotate AL left by 1 bit (shifting the output pattern)
     DEC BX           ; Decrease BX counter
    JNZ BACK         ; If BX is not zero, repeat the loop
    INT 03           ; Interrupt for program termination (debug breakpoint)
