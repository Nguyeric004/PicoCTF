#Challenge: strings it

#Objective
Find flag without running file

#Solution Steps
1. Download file into terminal 
    wget https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
2. Checked contents of directory
    ls
3. Verfied file "strings" sucessfully downloaded, checked contents of file
    cat strings
4. File contained human-unreadable data, searched for strings
    strings strings
5. Search returned large list of strings, filtered strings for flag related content
    strings strings | grep "pico"
6. Extracted flag from file
    flag: picoCTF{5tRIng5_1T_7f766a23}

#Learned
How to search for only strings within a file and refine search for specfic strings.