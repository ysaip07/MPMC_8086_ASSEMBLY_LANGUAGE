# 8086 Assembly Code: Reverse Copy of 8 Bytes

    MOV SI, 7000H    ; Load SI with the starting address of source data
    MOV DI, 8000H    ; Load DI with the starting address of destination data
    MOV CX, 0008H    ; Load CX with the number of bytes to copy (8 bytes)
    ADD SI, 07H      ; Move SI to the last byte of the 8-byte block
L1: MOV AL, [SI]      ; Load a byte from source
    MOV [DI], AL     ; Store it at destination
    DEC SI           ; Move SI backwards (reverse order copy)
    INC DI           ; Move DI forward
    DEC CX           ; Decrease loop counter
    JNZ L1           ; Repeat until CX becomes zero
    INT 03           ; Breakpoint for debugging (pauses execution for inspection)

Note:
 This code copies 8 bytes from memory at 7000H to 8000H in **reverse order**.
 After execution, 8000H will contain the reversed version of the data at 7000H.
 INT 03 is used for debugging.
