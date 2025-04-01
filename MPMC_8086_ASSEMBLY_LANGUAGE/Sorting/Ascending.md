# 8086 Assembly Code: ASCENDING ORDER

        MOV AX,0000     ; Initialize AX register (not used directly)
        MOV CL,06H      ; Load CL with 6 (outer loop counter)
        DEC CL          ; Decrement CL (5 iterations in total)
    X3: MOV CH,CL       ; Copy CL to CH (inner loop counter)
        MOV SI,3000H    ; Load SI with the starting address of the array
    X2: MOV AL,[SI]     ; Load AL with the byte at address SI
        INC SI          ; Increment SI to point to the next element
        CMP AL,[SI]     ; Compare AL with the next element
        JB L1           ; If AL < [SI], no swap needed, jump to L1
        XCHG AL,[SI]    ; Swap AL and [SI]
        DEC SI          ; Move SI back to previous element
        MOV [SI],AL     ; Store AL back at SI (completing swap)
        INC SI          ; Move SI forward again
    L1: DEC CH          ; Decrement CH (inner loop counter)
        JNE X2          ; If CH is not zero, repeat inner loop
        DEC CL          ; Decrement CL (outer loop counter)
        JNE X3          ; If CL is not zero, repeat outer loop
        INT 03          ; Interrupt to stop execution (debug breakpoint)
