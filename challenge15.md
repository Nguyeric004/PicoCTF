#Challenge: PW Crack 1

#Objective
Find the flag using the password checker script

#Solution Steps
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/12/level1.py 
    wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
2. Changed level.py script into executable
     chmod +x level1.py
3. Ran script
    python level1.py
4. Prompted password, exited script and checked file
    ctrl + c
    nano level1.py
5. Found password inside file, ran script and entered in password
    python level.py
    8713
6. Extracted flag from script
    flagpicoCTF{545h_r1ng1ng_1b2fd683}

#Learned
How to check the contents of a file inside terminal