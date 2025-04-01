# PACKED BCD TO UNPACKED BCD

    MOV SI,6000h  ; Load SI with memory address 6000h
    MOV AL,[SI]   ; Load the byte from [6000h] into AL
    MOV AH,AL     ; Copy AL into AH (preserve the original value)
    AND AL,0Fh    ; Mask AL to keep only the lower 4 bits (clear upper 4 bits)
    MOV CL,04h    ; Load CL with 4 (used for shifting)
    SHR AH,CL     ; Shift AH right by 4 bits (extract upper 4 bits)
    INT 03        ; Trigger a software breakpoint interrupt (used for debugging)
