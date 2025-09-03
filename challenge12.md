#Challenge: First Grep

#Objective
Find flag in file using grep

#Solution Steps
1. Download file into terminal 
    wget https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
2. Checked contents of directory
    ls
3. Verfied file "file" sucessfully downloaded, checked contents of file
    cat file
4. Contents is vast in human-unreadable format, searched specifically for flag related content
    grep "pico" file
5. Extracted flag from file
    flag: picoCTF{grep_is_good_to_find_things_dba08a45}

#Learned
How to use grep to search for specific strings.