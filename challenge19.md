#Challenge: PW Crack 5

#Objective
Find the right password in dictionary.txt file and get flag

#Solution Steps
1. Downloaded all necessary files
2. Opened level5.py file
    code level5.py
3. Removed user input prompt
    "user_pw = input("Please enter correct password for flag: ")"
4. Added function to read dictionary.txt file 
    with open("dictionary.txt", "r") as file:
        dictionary = file.readlines()
5. Added for loop to run all words inside dictionary.txt file against password checker
    def level_5_pw_check():
    for user_pw in dictionary:
        user_pw_hash = hash_pw(user_pw)
        print(user_pw)
        if user_pw_hash == correct_pw_hash:
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
    print("That password is incorrect")
6. Returned error, removed new line from dictionary and ran password checker
    with open("dictionary.txt", "r") as file:
    dictionary = file.readlines()
    dictionary = [word.strip("\n") for word in dictionary]
7. Extracted flag from password checker
    flag: picoCTF{h45h_sl1ng1ng_40f26f81}

#Learned
