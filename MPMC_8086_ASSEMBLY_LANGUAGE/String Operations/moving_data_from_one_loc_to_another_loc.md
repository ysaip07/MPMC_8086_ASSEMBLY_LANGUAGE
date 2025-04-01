# 8086 Assembly Code: Copy 8 Bytes Using REP MOVSB

MOV SI, 2000H    ; Load SI with the starting address of source data
MOV DI, 2008H    ; Load DI with the starting address of destination data
MOV CX, 0008H    ; Load CX with the number of bytes to copy (8 bytes)
REP              // Use REP MOVSB to copy data efficiently
MOVSB            ; Repeat MOVSB (Move Byte from DS:[SI] to ES:[DI]) CX times
INT 03           ; Breakpoint for debugging (pauses execution for inspection)

<!--
 Note:
 - This code copies 8 bytes from memory at 2000H to 2008H in **forward order**.
 - MOVSB automatically increments SI and DI after each byte transfer.
 - REP MOVSB repeats the operation CX times (8 times in this case).
 - INT 03 is used for debugging.
-->