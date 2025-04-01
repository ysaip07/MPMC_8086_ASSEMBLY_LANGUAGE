# 8086 Assembly Code: Delete a byte in given string

    MOV SI, 7000H    ; Load SI with the starting address of source data
    MOV DI, 8000H    ; Load DI with the starting address of destination data
    MOV BX, 6000H    ; Load BX with the address for comparison data
    MOV CX, 0005H    ; Load CX with the number of bytes to process (5 bytes)
    CLD              ; CLD (Clear Direction Flag) makes SI and DI increment after each operation
L1: MOV AL,[SI]      ; Load byte from source
    CMP AL, [BX]     ; Compare AL with the byte at BX
    JZ L2            ; If they match, jump to L2
    MOVSB            ; Otherwise, move byte from SI to DI
    LOOP L1          ; Decrement CX and repeat until CX = 0
    JMP L3           ; Jump to L3 to terminate
L2: INC SI           ; Increment SI for next storage
    DEC CX           ; Decrement CX counter
    REP              ; Repeat MOVSB while CX > 0
    MOVSB
L3: INT 03           ; Breakpoint for debugging (pauses execution for inspection)
