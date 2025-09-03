#Challenge: Insp3ct0r

#Objective
Kishor Balan tipped us off that the following code may need inspection: https://jupiter.challenges.picoctf.org/problem/41511/ 

#Solution Steps
1. Opened up link
    https://jupiter.challenges.picoctf.org/problem/41511/ 
2. Clicked on "What" tab
    found "I made a website"
3. Clicked on "How" tab
    found "I used these to make this site:
                        HTML
                        CSS
                    JS (JavaScript)"
4. Right clicked on website and clicked inspect, sifted through HTML elements in inspector tab
5. Extracted part 1/3 of flag nested in paragraph element
    "Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3"
6. Sifted through css elements in style editor tab, extracted part 2/3 of flag
    "/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */"
7. Looked through .js file in debugger tab, extracted part 3/3 of flag
    "/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?832b0699} */"
8. Compiled flag from all pieces
    flag: picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?832b0699}

#Learned
How to inspect the 3 main components of a website with the inspect tool as well as which tabs each element is located under