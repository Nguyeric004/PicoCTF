#Challenge: Big Zip

#Objective
Find the flag within the big zip file

#Solution Steps
1. Download all necessary files
    wget https://artifacts.picoctf.net/c/503/big-zip-files.zip
2. Checked contents of directory
    ls 
4. Made temp directory to unzip all files
    mkdir temp
5. Moved .zip file into temp directory
    mv temp big-zip-files.zip
6. Unzippped zip file
    unzip big-zip-files.zip file
7. Checked contents of directory
    ls
8. Found lots of files, searched for flag using recursive grep
    grep -r "picoCTF" temp
9. Extracted flag from search
    flag: picoCTF{gr3p_15_m4g1c_ef8790dc}

#Learned
How to use grep to search all files within a directory