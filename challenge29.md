#Challenge: Bit-O-Asm-3

#Objective
Figure out what is in the eax register then put your answer in the picoCTF flag format

#Solution Steps
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
2. Checked contents of directory
    ls
3. Found disassembler-dump0_c.txt file, checked contents of file
    nano disassembler-dump0_c.txt
4. Found various functions, went line by line and converted functions to human readable format
    <+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a => rbp-0xc = 0x9fe1a
    <+22>:    mov    DWORD PTR [rbp-0x8],0x4     => rbp-0x8 = 0x4
    <+29>:    mov    eax,DWORD PTR [rbp-0xc]     => eax = rbp-0xc = 0x9fe1a
    <+32>:    imul   eax,DWORD PTR [rbp-0x8]     => eax = eax * rbp-0x8 = eax * 0x4
    <+36>:    add    eax,0x1f5                   => eax = eax + 0x1f5           
    <+41>:    mov    DWORD PTR [rbp-0x4],eax     => rbp-0x4 = eax
    <+44>:    mov    eax,DWORD PTR [rbp-0x4]     => eax = rbp-0x4
5. Convereted values from hex to decimal using CyberChef Base recipe with radix 16
    rbp-0xc = 0x9fe1a                => rbp-0xc = 654874
    rbp-0x8 = 0x4                    => rbp-0x8 = 4
    eax = rbp-0xc = 0x9fe1a          => eax = rbp-0xc = 654874
    eax = eax * rbp-0x8 = eax * 0x4  => eax = eax * rbp-0x8 = eax * 4
    eax = eax + 0x1f5                => eax = eax + 501
    rbp-0x4 = eax                    => rbp-0x4 = eax
    eax = rbp-0x4                    => eax = rbp-0x4
6. Followed order of functions to solve for eax value
    eax = (654874 * 4) + 501 = 2619997
7. Put eax value in picoCTF flag format
    flag: picoCTF{2619997}

#Learned
How to perform mathematical operations in assembly