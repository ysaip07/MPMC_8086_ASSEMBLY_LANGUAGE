# CODE CONVERSION ASCII TO BCD

    MOV SI,6000
    MOV AX,[SI]
    AND AL,0F   //AND AX,0F0F
    AND AH,0F
    MOV CL,04
    SHL AH,CL
    OR AH,AL
    INT 03
