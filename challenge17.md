#Challenge: PW Crack 3

#Objective
Find the correct password for the flag using the password checker and the hash file

#Solution Steps
1. Download all necessary files
    wget https://artifacts.picoctf.net/c/18/level3.py
    wget https://artifacts.picoctf.net/c/18/level3.flag.txt.enc
    wget https://artifacts.picoctf.net/c/18/level3.hash.bin
2. Made script into executable
    chmod +x level3.py
3. Examined contents of script file
    nano level3.py
4. Found list of possible passwords within file
    pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]
5. Examined contents of hash file
    bvi level3.hash.bin
6. Found hash value
    16 02 6D 60 FF 9B 54 41 0B 34 35 B4 03 AF D2 26
7. Input possible passwords through MD5 hash algorithm
    8799: e6051b3bfe716cc4a38c2f39ec199873
    d3ab: 2b268941ebe6a029484266060fa70243
    1ea2: 8f60458cc64243ba3b88f8bfcfa269eb
    acaf: 3df13964fd043dad82ac80b931a71f2d
    2295: 16026d60ff9b54410b3435b403afd226
    a9de: b9cce7a7a688e9dbca3dd7f0469de54
    6f3d: cbdc1d56d54a78a5ba0543528f85af6a
8. Found matching hash value, entered password into script
    python level3.py
    2295
9. Extracted flag from script
    flag: picoCTF{m45h_fl1ng1ng_6f98a49f}

#Learned
How to tell if a hash is in MD5, SHA-1, SHA-256, SHA-512, and bcrypt