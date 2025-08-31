#Challenge: Obedient Cat

#Objective
Find flag hidden in plain sight

#Solution Steps
1.Examined contents of directory
    ls
2. Found README.txt, examined contents of readme.txt
    cat README.txt
3. Did not find flag inside file, downloaded provided flag file
    wget https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag
4. Examined contents of directory
    ls
5. Found flag file, examined contents of flag
    cat flag
6. Found flag
    flag: picoCTF{s4n1ty_v3r1f13d_28e8376d}

#Learned
How to download files into shell using wget    

