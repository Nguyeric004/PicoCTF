#Challenge: What's a net cat

#Objective
Use netcat to get the flag

#Solution Steps
1. Examined files in directory
    ls
2. Ran netcat to see its commands and parameters
    nc
3. Found [destination] [port] parameters and executed command using those parameters
    nc jupiter.challenges.picoctf.org 64287
4. Server returned flag
    flag: picoCTF{nEtCat_Mast3ry_284be8f7}

#Learned
How to use nc to connect to a server and port