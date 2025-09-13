#Challenge: PW Crack 2

#Objective
Find the flag using the password checker script on the flag file

#Solution Steps
1. Download all necessary files
    wget https://artifacts.picoctf.net/c/13/level2.py
    wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
2. Changed level2.py into executable
    chmod +x level2.py
3. Examined script file
    nano level2.py
4. Found encrypted password inside file
    user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)
5. Decrypted password
    user_pw == chr(d) + chr(e) + chr(7) + chr(6)
6. Ran script and extracted flag 
    flag: picoCTF{tr45h_51ng1ng_489dea9a}


#Learned
How to scan file and decode password encryption