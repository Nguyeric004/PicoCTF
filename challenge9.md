#Challenge: Tab, Tab, Attack

#Objective
Use tabcomplete to find flag

#Solution Steps
1. Download file into terminal 
    wget https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
2. Chcked contents of directory
    ls
3. Confirmed donwload of Addadshashanammu.zip file, examined contents of file
    cat Addadshashanammu.zip
4. Contents were not human-readable, unzipped file
    unzip Addadshashanammu.zip
5. Chcked contents of directory
    ls
6. Confirmed Addadshashanammu.zip was successfully unzipped, checked contents of unzipped directory
    cd Addadshashanammu
7. Revealed another directory, utilized tab completion to navigate to end of directory
    cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
8. Check contents of directory
    ls
9. Found file fang-of-haynekhtnamet, checked contents of file
    cat fang-of-haynekhtnamet
10. File does not contain flag, executed file in terminal
    chmod +x fang-of-haynekhtnamet
    ./fang-of-haynekhtnamet
11. Execution of file returned flag
    flag: picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}

#Learned
How to use tab complete for easier navigation and input of files and directories and how to zip and unzip files within terminal.