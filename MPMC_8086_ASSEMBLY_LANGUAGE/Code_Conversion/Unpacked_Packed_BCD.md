<!--
    MOV SI,6000
    MOV AL,[SI]
    INC SI
    MOV AH,[SI]
    MOV CL,04
    SHR AH,CL
    OR AL,AH
    INT 03
-->