#Challenge: PW Crack 4

#Objective
Find the correct password for the flag using the password checker and the hash file but with 100 possibilities of passwords

#Solution Steps
1. Downloaded all necessary files
2. Opened level4.py file
    code level4.py
3. Removed user input line of code 
    "user_pw = input("Please enter correct password for flag: ")"
4. Added for loop in using passwords from password bank and ran code
    def level_4_pw_check():
    for user_pw in pos_pw_list:
        user_pw_hash = hash_pw(user_pw)
        if( user_pw_hash == correct_pw_hash ):
            print("Welcome back... your flag, user:")
            print("pw")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
        print("That password is incorrect")
5. Outputted variable "pos_pw_list" not defined, moved variable above function call and executed password checker
    pos_pw_list = ["8c86", "7692", "a519", "3e61", "7dd6", "8919", "aaea", "f34b", "d9a2", "39f7", "626b", "dc78", "2a98", "7a85", "cd15", "80fa", "8571", "2f8a", "2ca6", "7e6b", "9c52", "7423", "a42c", "7da0", "95ab", "7de8", "6537", "ba1e", "4fd4", "20a0", "8a28", "2801", "2c9a", "4eb1", "22a5", "c07b", "1f39", "72bd", "97e9", "affc", "4e41", "d039", "5d30", "d13f", "c264", "c8be", "2221", "37ea", "ca5f", "fa6b", "5ada", "607a", "e469", "5681", "e0a4", "60aa", "d8f8", "8f35", "9474", "be73", "ef80", "ea43", "9f9e", "77d7", "d766", "55a0", "dc2d", "a970", "df5d", "e747", "dc69", "cc89", "e59a", "4f68", "14ff", "7928", "36b9", "eac6", "5c87", "da48", "5c1d", "9f63", "8b30", "5534", "2434", "4a82", "d72c", "9b6b", "73c5", "1bcf", "c739", "6c31", "e138", "9e77", "ace1", "2ede", "32e0", "3694", "fc92", "a7e2"]

    level_4_pw_check()
6. Extracted flag from password checker
    flag: picoCTF{fl45h_5pr1ng1ng_d770d48c}

#Learned
How to write into files using nano and input for loops into files
