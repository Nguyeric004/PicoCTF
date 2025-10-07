#Challenge: Bit-O-Asm-2

#Objective
Figure out what is in the eax register then put your answer in the picoCTF flag format

#Solution Steps
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
2. Checked contents of directory 
    ls
3. Found disassembler-dump0_a.txt file, checked contents of file    
    nano disassembler-dump0_a.txt
4. Found eax register pointed to variable rbp-0x4
    mov    eax,DWORD PTR [rbp-0x4]
4. Looked at variable rbp-0x4
    mov    DWORD PTR [rbp-0x4],0x9fe1a
5. Found value 0x9fe1a, pasted value into CyberChef
6. Set recipe to From Base and set Radix to 16
7. Put output in picoCTF flag format
    flag: picoCTF{654874}

#Learned
How push and pop functions work as well how to set stack frame