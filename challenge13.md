#Challenge: where are the robots

#Objective
 Find the robots on https://jupiter.challenges.picoctf.org/problem/36474/

#Solution Steps
1. Opened up the website
    https://jupiter.challenges.picoctf.org/problem/36474/
2. Inspected elements of website
    Inspector
    Style Editor
    Debugger
3. Found nothing out of the ordinary, checked robots.txt of website
    https://jupiter.challenges.picoctf.org/problem/36474/robots.txt
4. Found disallowed rule "/477ce.html", checked url of disallowed rule
    https://jupiter.challenges.picoctf.org/problem/36474/477ce.html
5. Extracted flag from page
    Flag: picoCTF{ca1cu1at1ng_Mach1n3s_477ce}

#Learned
Robots.txt is a file used to tell web crawler robots what to not index and is a hidden page.