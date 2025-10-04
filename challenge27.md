#Challenge: Bit-O-Asm-1

#Objective
Figure out what is in the eas register inside assembly dump file and put it inside the picoCTF flag format

#Solution Steps
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
2. Checked contents of directory
    ls
3. Found disassembler-dump0_a.txt file, checked contents of file    
    nano disassembler-dump0_a.txt
4. Found line with eax register along with contents
    <+15>:    mov    eax,0x30
5. Pasted hexadecimal value inside CyberChef
6. Placed From Base operation inside Recipe section and set Radix to 16
7. Placed output in flag format
    flag: picoCTF{48}

#Learned
What types of data registers are used in assembly and some of the commands inside assembly