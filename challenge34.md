#Challenge: GDB baby step 4

#Objective
Find the constant that the eax register is multiplied by and put it in picoCTF flag format

#Solution Steps
1. Downloaded all necessary files
    wget (https://artifacts.picoctf.net/c/532/debugger0_d)
2. Checked contents of directory 
    ls
3. Found debugger0_d file, made file executable
    chmod +x debugger0_d
4. Opened file with GDB
    gdb debugger0_d
5. Disassembled file
    disassemble main

    0x000000000040111c <+0>:     endbr64
    0x0000000000401120 <+4>:     push   %rbp
    0x0000000000401121 <+5>:     mov    %rsp,%rbp
    0x0000000000401124 <+8>:     sub    $0x20,%rsp
    0x0000000000401128 <+12>:    mov    %edi,-0x14(%rbp)
    0x000000000040112b <+15>:    mov    %rsi,-0x20(%rbp)
    0x000000000040112f <+19>:    movl   $0x28e,-0x4(%rbp)
    0x0000000000401136 <+26>:    movl   $0x0,-0x8(%rbp)
    0x000000000040113d <+33>:    mov    -0x4(%rbp),%eax
    0x0000000000401140 <+36>:    mov    %eax,%edi
    0x0000000000401142 <+38>:    call   0x401106 <func1>
    0x0000000000401147 <+43>:    mov    %eax,-0x8(%rbp)
    0x000000000040114a <+46>:    mov    -0x4(%rbp),%eax
    0x000000000040114d <+49>:    leave
    0x000000000040114e <+50>:    ret

6. Noticed func1 was called inside main, looked at list of functions 
    info functions
7. Found func1, disassembled file
    disassemble func1
8. Found imul instruction with value 0x3269, translated value into decimal format
    p/d 0x3269
9. Placed value in flag format
    flag: picoCTF{12905}

#Learned
How to view functions inside a debugger