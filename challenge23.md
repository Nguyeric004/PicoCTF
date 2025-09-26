#Challenge: keygenme-py

#Objective
Find the flag within the python filew

#Solution Steps
1. Download all necessary files
    wget https://mercury.picoctf.net/static/9055e7d35f5f4646338a1734aea0dda5/keygenme-trial.py
2. Checked contents of directory
    ls
3. Found keygenme-trial.py file, examined contents of file
    nano keygenme-trial.py 
4. Found function that puts together key
    key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"
    key_part_dynamic1_trial = "xxxxxxxx"
    key_part_static2_trial = "}"
    key_full_template_trial = (key_part_static1_trial + key_part_dynamic1_trial + key_part_static2_trial)
5. Checked further and found function that checked trial key, isolated functions that converted key to sha256
        if key[i] != hashlib.sha256(username_trial).hexdigest()[4]:
            return False
        else:
            i += 1

        if key[i] != hashlib.sha256(username_trial).hexdigest()[5]:
            return False
        else:
            i += 1

        if key[i] != hashlib.sha256(username_trial).hexdigest()[3]:
            return False
        else:
            i += 1

        if key[i] != hashlib.sha256(username_trial).hexdigest()[6]:
            return False
        else:
            i += 1

        if key[i] != hashlib.sha256(username_trial).hexdigest()[2]:
            return False
        else:
            i += 1

        if key[i] != hashlib.sha256(username_trial).hexdigest()[7]:
            return False
        else:
            i += 1

        if key[i] != hashlib.sha256(username_trial).hexdigest()[1]:
            return False
        else:
            i += 1

        if key[i] != hashlib.sha256(username_trial).hexdigest()[8]:
            return False
6. Found the corresponding 8 digits in order that make up the dynamic part of the key
    45362718
7. Made new python file to generate dynamic key
    nano converter.py
8. Used format of conversion already inside source code to model conversion function of each key
    if key[i] != hashlib.sha256(username_trial).hexdigest()[4]:
        return False
    else:
        i += 1
        
    vvvvvvvvv

    convert = hashlib.sha256(username_trial).hexdigest();
9. Found trial username within source code
    username_trial = "FRASER"
10. Put trial username inside conversion function
    convert = hashlib.sha256("FRASER").hexdigest();
11. Added other pieces of key and output full key
    import hashlib

    convert = hashlib.sha256("FRASER").hexdigest()

    key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"
    key_part_dynamic1_trial = (convert[4] + convert[5] + convert[3] + convert[6] + convert[2] + convert[7] + convert[1] + convert[8])
    key_part_static2_trial = "}"

    key_full_template_trial = (key_part_static1_trial + key_part_dynamic1_trial + key_part_static2_trial)

    print(key_full_template_trial)
12. Ran coversion python script
    python converter.py
13. Extracted key from output 
    key: picoCTF{1n_7h3_|<3y_of_ac73dc29}
14. Made keygenme-trial.py file an executable
    chmod +x keygenme-trial.py
15. Ran keygenme python script and navigated to license activation 
    python keygenme-trial.py
    c
16. Tested key
    picoCTF{1n_7h3_|<3y_of_ac73dc29}
17. License activation was successful, the key doubled as the flag 
    flag: picoCTF{1n_7h3_|<3y_of_ac73dc29}

#Learned
How to reverse engineer a password by looking at the method of encryption and checking of inputs; as well as how to make a script that generates the key based on the method of reverse engineering