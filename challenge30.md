#Challenge: Bit-O-Asm-4

#Objective
Figure out what is in the eax register then put your answer in the picoCTF flag format

#Solution Steps
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt
2. Checked contents of directory
    ls
3. Found disassembler-dump0_d.txt file, checked contents of file
    nano disassembler-dump0_d.txt
4. Found various functions, went line by line and converted functions to human readable format
    <+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a  => rbp-0x4 = 0x9fe1a
    <+22>:    cmp    DWORD PTR [rbp-0x4],0x2710   => compare rbp-0x4 with 0x2710
    <+29>:    jle    0x55555555514e <main+37>     => jump to +37 if rbp-0x4 less or equal to 0x2710
    <+31>:    sub    DWORD PTR [rbp-0x4],0x65     => rbp-0x4 = rbp-0x4 - 0x65
    <+35>:    jmp    0x555555555152 <main+41>     => jump to + 41
    <+37>:    add    DWORD PTR [rbp-0x4],0x65     => rbp-0x4 = rbp-0x4 + 0x65
    <+41>:    mov    eax,DWORD PTR [rbp-0x4]      => eax = rbp-0x4 
5. Converted hexadecimal values with decimal values
    <+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a  => rbp-0x4 = 654874
    <+22>:    cmp    DWORD PTR [rbp-0x4],0x2710   => compare rbp-0x4 with 10000
    <+29>:    jle    0x55555555514e <main+37>     => jump to +37 if rbp-0x4 less or equal to 10000     
    <+31>:    sub    DWORD PTR [rbp-0x4],0x65     => rbp-0x4 = rbp-0x4 - 101
    <+35>:    jmp    0x555555555152 <main+41>     => jump to +41
    <+37>:    add    DWORD PTR [rbp-0x4],0x65     => rbp-0x4 = rbp-0x4 + 101
    <+41>:    mov    eax,DWORD PTR [rbp-0x4]      => eax = rbp-0x4 
6. Substituted variables with actual values and left only relevant operations
    <+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a  => rbp-0x4 = 654874
    <+22>:    cmp    DWORD PTR [rbp-0x4],0x2710   => compare 654874 with 10000
    <+29>:    jle    0x55555555514e <main+37>     => jump to +37 if 654874 less or equal to           
    <+31>:    sub    DWORD PTR [rbp-0x4],0x65     => rbp-0x4 = 654874 - 101
    <+35>:    jmp    0x555555555152 <main+41>     => jump to +41
    <+41>:    mov    eax,DWORD PTR [rbp-0x4]      => eax = rbp-0x4 
7. Followed order of functions to solve for eax value
    eax = 654874 - 101 = 654773
8. Put eax value in picoCTF flag format
    flag: picoCTF{654773}

#Learned
How to make if-like functions using cmp, jmp, jle 