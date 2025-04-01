# UNPACKED BCD TO PACKED BCD

    MOV SI,6000h  ; Load SI with memory address 6000h
    MOV AL,[SI]   ; Load the first byte from [6000h] into AL
    INC SI        ; Move SI to the next memory location (6001h)
    MOV AH,[SI]   ; Load the second byte from [6001h] into AH
    MOV CL,04h    ; Load CL with 4 (used for shifting)
    SHR AH,CL     ; Shift AH right by 4 bits (extract upper 4 bits)
    OR AL,AH      ; Combine AL with shifted AH using OR operation
    INT 03        ; Trigger a software breakpoint interrupt (used for debugging)
