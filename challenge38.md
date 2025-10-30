#Challenge: Picker IV

#Objective
Figure out how the program works and find the flag

#Solution Steps
1. Download all necessary files
    wget https://artifacts.picoctf.net/c/527/picker-IV.c
    wget https://artifacts.picoctf.net/c/527/picker-IV
2. Checked contents of directory
    ls
3. Found picker-IV.c and picker-IV, checked type of file 
    picker-IV.c = ASCII text
    picker-IV = LSB executable
5. Checked contents of picker-IV
    nano picker-IV
6. File is not human readable, tried checking contents of picker-IV.c
    nano picker-IV.c
7. Found functions that ask for finding and jumping to a hex address using user input and a function that prints the flag 
    int main() {
        signal(SIGSEGV, print_segf_message);
        setvbuf(stdout, NULL, _IONBF, 0); // _IONBF = Unbuffered

        unsigned int val;
        printf("Enter the address in hex to jump to, excluding '0x': ");
        scanf("%x", &val);
        printf("You input 0x%x\n", val);

        void (*foo)(void) = (void (*)())val;
        foo();
    }

    int win() {
        FILE *fptr;
        char c;

        printf("You won!\n");
        // Open file
        fptr = fopen("flag.txt", "r");
        if (fptr == NULL)
        {
            printf("Cannot open file.\n");
            exit(0);
        }

        // Read contents from file
        c = fgetc(fptr);
        while (c != EOF)
        {
            printf ("%c", c);
            c = fgetc(fptr);
        }

        printf("\n");
        fclose(fptr);
    }
8. Disassembled picker-IV
    gdb picker-IV
    disassemble main
9. Did not find anything, tried checking functions
    info functions
10. Found win function with address 0x040129e, ran program with address
    nc saturn.picoctf.net 62045
    40129e
11. Extracted flag from output
    flag: picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_01672a61}

#Learned
How to exploit reading binary addresses