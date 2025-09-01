#Challenge: Bases

#Objective
Decipher given string to get human-readable flag

#Solution Steps
1. String seems to be converted to base format, try to revery from base 32 using CyberChef
    Input:bDNhcm5fdGgzX3IwcDM1
    From Base32
2. Output was not human-readable, attempted from base 58
    Input:bDNhcm5fdGgzX3IwcDM1
    From Base58
3. Output was not human-readable, attempted from base 64
    Input:bDNhcm5fdGgzX3IwcDM1
    From Base64
4. Output was human readable, extracted flag from output
    flag: picoCTF{l3arn_th3_r0p35}

#Learned
How to recognize when string is in base format and CyberChef has auto sensing tool that can tell what operation can turn string into human readable text