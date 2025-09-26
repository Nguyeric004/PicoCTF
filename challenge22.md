#Challenge: Vault Door Training

#Objective
Find the flag within the source code of the vault java file

#Solution Steps
1. Download all necessary files
    wget https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java
2. Checked contents of java file
    nano VaultDoorTraining.java
3. Extracted password from source code of java file
    password: picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}
4. Made java file executable
    chmod +x VaultDoorTraining.java
5. Ran java file
    java VaultDoorTraining.java
6. Prompted password input, tried password found in source code
    picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}
7. Password was correct and doubles as the flag 
    flag: picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}

#Learned
How to check source code of java file and run it in terminal