
<!--
    MOV SI,6000
    MOV AL,[SI]
    MOV AH,AL
    AND AL,0F
    MOV CL,04
    SHR AH,CL
    INT 03
-->