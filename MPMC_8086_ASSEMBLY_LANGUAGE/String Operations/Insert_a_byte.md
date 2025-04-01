# 8086 Assembly Code: Conditional Byte Copying with Comparison

    MOV SI, 3000H    ; Load SI with the starting address of source data
    MOV DI, 4000H    ; Load DI with the starting address of destination data
    MOV BX, 5000H    ; Load BX with the address for comparison data
    MOV CX, 0005H    ; Load CX with the number of bytes to process (5 bytes)
    CLD              ; CLD (Clear Direction Flag) makes SI and DI increment after each operation
L1: MOV AL,[SI]      ; Load byte from source
    CMP AL, [BX]     ; Compare AL with the byte at BX
    JZ L2            ; If they match, jump to L2
    MOVSB            ; Otherwise, move byte from SI to DI
    LOOP L1          ; Decrement CX and repeat until CX = 0
    JMP L3           ; Jump to L3 to terminate
L2: MOVSB            ; Move byte from SI to DI
    MOV BX, 6000H    ; Change BX to a new memory location
    MOV AL, [BX]     ; Load a byte from new memory location
    MOV [DI], AL     ; Store it at DI
    DEC CX           ; Decrement CX counter
    INC DI           ; Increment DI for next storage
    REP              ; Repeat MOVSB while CX > 0
    MOVSB
L3: INT 03           ; Breakpoint for debugging (pauses execution for inspection)

## Note

1.This code compares each byte from 3000H with a byte at 5000H.
2.If a byte matches, it fetches new data from 6000H and stores it.
3.Otherwise, it copies the byte from 3000H to 4000H.
4.INT 03 is used for debugging;
