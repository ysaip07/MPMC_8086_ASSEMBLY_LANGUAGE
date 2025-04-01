<!--
    MOV SI,6000
    MOV AL,[SI]
    MOV AH,AL
    AND AL,0F
    MOV CL,04
    SHR AH,CL
    OR AL,30    //OR AX,3030
    OR AH,30
    INT 03
-->