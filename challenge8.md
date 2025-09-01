#Challenge: Wave a flag

#Objective
Find flag in program by using help flags

#Solution Steps
1. Download file into terminal 
    wget https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
2. Examine contents of directory to ensure file is there
    ls
3. File is confirmed to have successfully downloaded, make file executable
    chmod +x warm
4. Run file 
    ./warm
5. Execution prompts user to run file with -h command, run file with -h
    ./warm -h
6. Execution provides flag
    flag: picoCTF{b1scu1ts_4nd_gr4vy_30e77291}

#Learned
How to make a file executable and run file in addition to running its help tools