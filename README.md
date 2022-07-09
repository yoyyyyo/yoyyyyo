```asm
segment .text
global _start
_start:
    mov ecx, 0x79
    call b
    sub ecx, 0xa
    call b
    add ecx, 0xa
a:
    push ebx
    call b
    pop ebx
    inc ebx
    cmp ebx, 5
    jz c
    jmp a
b:
    mov eax, 4
    mov ebx, 1
    push ecx
    mov ecx, esp
    mov edx, 1
    int 0x80
    pop ecx
    ret
c:
    sub ecx, 0xa
    call b
    sub ecx, 0x65
    call b
    mov eax, 1
    mov ebx, 0
    int 0x80
```
