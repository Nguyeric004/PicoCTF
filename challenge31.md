#Challenge: GDB baby step 1

#Objective
Figure out what is in the eax register then put your answer in the picoCTF flag format

#Solution Steps
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/512/debugger0_a
2. Checked contents of directory
    ls
3. Found debugger0_a file, tried using gdb to debug
    gdb
    disassemble main
4. Debugging successful, found 0x86342 value moved into eax register. 
5. Used CyberChef From Base recipe with radix 16 to convert hexadecimal value to decimal
    549698
6. Placed value in flag format
    flag: picoCTF{549698}
#Learned
How to disassemble assembly file using gdb