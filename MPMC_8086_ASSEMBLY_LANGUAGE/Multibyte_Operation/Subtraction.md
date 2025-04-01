# MULTIBYTE SUBTRATION

        MOV AX,0000     ; Clear AX register (not strictly necessary but safe practice)
        MOV SI,4000h    ; Load SI with source address 4000h
        MOV BX,5000h    ; Load BX with second source address 5000h
        MOV DI,6000h    ; Load DI with destination address 6000h
        MOV CL,08h      ; Load loop counter with 8 (process 8 bytes)
    L1: MOV AL,[SI]     ; Load byte from memory at SI into AL
        SUB AL,[BX]     ; Subtract byte at BX from AL
        MOV [DI],AL     ; Store result at memory location DI
        INC SI          ; Move to next byte in first source array
        INC BX          ; Move to next byte in second source array
        INC DI          ; Move to next byte in destination array
        DEC CL          ; Decrease loop counter
        JNE L1          ; If CL is not zero, repeat loop
        INT 03          ; Trigger a software breakpoint interrupt (used for debugging)
