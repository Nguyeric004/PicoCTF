#Challenge:GDB baby step 2

#Objective
Figure out what is in the eax register then put your answer in the picoCTF flag format

#Solution Steps
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/512/debugger0_a
2. Checked contents of directory
    ls
3. Found debugger0_a file, tried using gdb to debug
    gdb debugger0_b
    disassemble main
4. Found assembly function, simplified functions         
    0x0000000000401115 <+15>: movl $0x1e0da,-0x4(%rbp)   =>  variable -0x4 = 0x1e0da
    0x000000000040111c <+22>: movl $0x25f,-0xc(%rbp)     =>  variable -0xc = 0x25f
    0x0000000000401123 <+29>: movl $0x0,-0x8(%rbp)       =>  variable -0x8 = 0x0 
    0x000000000040112a <+36>: jmp 0x401136 <main+48>     =>  move to line 48   
    0x000000000040112c <+38>: mov -0x8(%rbp),%eax        =>  eax = -0x8        
    0x000000000040112f <+41>: add %eax,-0x4(%rbp)        =>  -0x4 += -0x8          
    0x0000000000401132 <+44>: addl $0x1,-0x8(%rbp)       =>  -0x8 += 1          
    0x0000000000401136 <+48>: mov -0x8(%rbp),%eax        =>  eax = -0x8       
    0x0000000000401139 <+51>: cmp -0xc(%rbp),%eax        =>  compare eax and -0xc 
    0x000000000040113c <+54>: jl 0x40112c <main+38>      =>  if eax < -0xc jump to line 38   
    0x000000000040113e <+56>: mov -0x4(%rbp),%eax        =>  eax = -0x4
5. Simplified further and replaced hexadecimal strings with numbers
    0x0000000000401115 <+15>: movl $0x1e0da,-0x4(%rbp)   =>  variable A = 123098
    0x000000000040111c <+22>: movl $0x25f,-0xc(%rbp)     =>  variable B = 607
    0x0000000000401123 <+29>: movl $0x0,-0x8(%rbp)       =>  variable C = 0 
    0x000000000040112a <+36>: jmp 0x401136 <main+48>     =>  jump to line 48   
    0x000000000040112c <+38>: mov -0x8(%rbp),%eax        =>  eax = C        
    0x000000000040112f <+41>: add %eax,-0x4(%rbp)        =>  A += C          
    0x0000000000401132 <+44>: addl $0x1,-0x8(%rbp)       =>  C += 1          
    0x0000000000401136 <+48>: mov -0x8(%rbp),%eax        =>  eax = C       
    0x0000000000401139 <+51>: cmp -0xc(%rbp),%eax        =>  compare eax and B 
    0x000000000040113c <+54>: jl 0x40112c <main+38>      =>  if eax < B jump to line 38   
    0x000000000040113e <+56>: mov -0x4(%rbp),%eax        =>  eax = A 
6. Simplified fucntion to loop and calculated value of eax
    A = 0x25f
    B = 607
    C = 0
    while C < B:
        A += C
        C ++
    eax = A = 307659
7. Placed value in flag format
    flag: picoCTF{307659}

#Learned
How to disassemble a debugger file and translate assembly loop logic into python loop logic. Alternatively learned about putting a breakpoint in file so that you can examine current value of a register.
