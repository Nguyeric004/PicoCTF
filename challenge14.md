#Challenge: Python Wrangling

#Objective
Find the flag inside a flag.txt.en file using a python script with the password located in pw.txt

#Solution Steps
1. Download all necessary files
    wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/ende.py  
    wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/pw.txt
    wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/flag.txt.en   
2. Looked at python manual
    man python
3. Found python commands, made python script executable
    chmod +x ende.py
4. Ran python script
    python ende.py
5. Execution prompted additional options to specify type of actions script has: '-e','-d','-h', used '-h' for help
    python ende.py -h
6. Returned example use, examined contents of pw.txt to paste into password prompt and executed python script with password
    cat pw.txt
    python ende.py -d flag.txt.en
7. Extracted password from script
    flag: picoCTF{4p0110_1n_7h3_h0us3_67c6cc96}

#Learned
