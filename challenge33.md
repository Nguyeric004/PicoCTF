#Challenge: GDB baby step 3

#Objective
Find the memory that a constant has been loaded into using the GDB command x/4xb. Place the memory bytes in the picoCTF flag format

#Solution Steps
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/531/debugger0_c
2. Checked contents of directory
    ls
3. Found debugger0_c, ran file with GDB
    gdb debugger0_c
4. Disassembled file 
    disassemble main

    0x0000000000401106 <+0>:     endbr64 
    0x000000000040110a <+4>:     push   %rbp
    0x000000000040110b <+5>:     mov    %rsp,%rbp
    0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
    0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
    0x0000000000401115 <+15>:    movl   $0x2262c96b,-0x4(%rbp)
    0x000000000040111c <+22>:    mov    -0x4(%rbp),%eax
    0x000000000040111f <+25>:    pop    %rbp
    0x0000000000401120 <+26>:    ret    
5. Added breakpoint at line 16 to view contents of variable -0x4
    b *0x040111c
6. Ran program
    r
7. Examined contents of variable using given command
    x/4xb rbp-0x4
6. Extracted flag from output
    flag: picoCTF{0x6bc96222}

#Learned
How to view contents of a variable after running a program until breakpoint
