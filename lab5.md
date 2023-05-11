## Lab 5 (Report 3)
# Grep Command
Grep is a command-line tool used to search for text from a file or another command's output. It will return the lines that contain the text you are looking for.
The command can search for exact matches, partial matches, or patterns using regular expressions. Like most commands, there are many options or alternative ways to use this command.
Here, I will be showing you 4 different ways of using grep, each highlighting different functionalities that may be relevant in your own use of the command.

# '-i' option
This option allows us to search for text like normal, but ignores uppercase letters. Without -i, grep would be case sensitive but with it, now it isn't. This might be helpful in cases
where you don't care for exact matches and just want any form of the sequence of characters you are looking for. For example, inputting "bye" after -i will return all lines containing
BYE, bYe, ByE, etc.

Source: en.wikibooks.org/wiki/Grep This link takes you to a wikipedia type of page and in it shows a whole variety of command-line options for grep. I will be using this source mainly
to find out most, if not, all the command-line options for grep.

Example 1: The file we are using is ./biomed/rr74.txt (cd into ~/stringsearch/stringsearch-data/technical if you haven't already)

Our input:
```
grep -i "inDUCED" ./biomed/rr74.txt
```
Our output:
```
        severe hypoxia-induced pulmonary hypertension. The
        chemical-induced (monocrotaline) or genetic (fawn-hooded
        upregulation in the murine lung with severe hypoxia-induced
```
The input in the command line "inDUCED" will still return all of the lines in the file that have the same spelling, igorning case sensitivity. This is why we still see "induced."
If we had not had -i, we wouldn't get any lines back.

Example 2: The file we are using now is ./911report/chapter-9.txt

Our input:
```
grep -i "HJIJACK" ./911report/chapter-9.txt
```
Our output:
```
                the 17 minutes from the crash of the hijacked American Airlines Flight 11 into
                the 56 minutes from the crash of the hijacked United Airlines Flight 175 into
            At 8:46:40, the hijacked American Airlines Flight 11 flew into the upper portion of
            At 9:03:11, the hijacked United Airlines Flight 175 hit 2 WTC (the South Tower) from
            At 9:37, the west wall of the Pentagon was hit by hijacked American Airlines Flight
                because of the warning of an approaching hijacked aircraft passed along by the FBI.
```
Here, we see that although the inputted string we're looking is "HIJACK" in all capital letters, the file doesn't have that yet still returns the lines containing the lowercase version.
Note that it is even returning "hijacked" because that word itself has the word "hijack" in it.
