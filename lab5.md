## Lab 5 (Report 3)
# Grep Command
Grep is a command-line tool used to search for text from a file or another command's output. It will return the lines that contain the text you are looking for.
The command can search for exact matches, partial matches, or patterns using regular expressions. Like most commands, there are many options or alternative ways to use this command.
Here, I will be showing you 4 different ways of using grep, each highlighting different functionalities that may be relevant in your own use of the command.

# '-i' option
This option allows us to search for text like normal, but ignores uppercase letters. Without -i, grep would be case sensitive but with it, now it isn't. This might be helpful in cases
where you don't care for exact matches and just want any form of the sequence of characters you are looking for. For example, inputting "bye" after -i will return all lines containing
BYE, bYe, ByE, etc.

Source: [Wikibooks](en.wikibooks.org/wiki/Grep) This link takes you to a wikipedia type of page and in it shows a whole variety of command-line options for grep. I will be using this source mainly
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
# '-v' option
This option is known as "inverse match." In simpler terms, this means matching all lines in a file that do NOT contain the inputted text. This is helpful when searching for lines that do not contain the unwanted text that you inputted.

Source: [Wikibooks](en.wikibooks.org/wiki/Grep)
        I also used ChatGPT to ask about how to take multiple command-line arguments, which is relevant for example 2.

Example 1: The file we will be using is ./biomed/rr74.txt again (again, we're assuming you're in ./technical)

Our input:
```
grep -v "a" ./biomed/rr74.txt
```
Our output:
```



        Introduction
        immunohistochemistry.



          Mice


          Exposure environments




          Western blotting


          with A
          260 /A
          diluted in depC H
          determined using 18 S rRNA primers/probes (Applied
          RNA.


          Immunohistochemistry


          2 -, NO
          (Ionics Instrument Business Group, Boulder, CO, USA).


          P < 0.05 is considered



        Results

          respectively;
          P < 0.001).


          Western blotting
          As shown in Fig. 2, lung eNOS protein levels were


          3.5-fold (Fig. 3).


          Immunohistochemistry
          shown).





        Discussion
        development.
        21].
        detection in the lungs of hypoxic, hypertensive mice.
        flushed with 10% O
        different species in cultures [ 31, 32, 33, 34, 35, 36, 37]
        production of NO
        piglets


        Conclusion
        considering studies using NOS-deficient mice. The present




```
Here, we get a long output of lines that don't contain the letter "a" which is technically what we're looking for. However, as you can see, we have a lot of empty lines that we might not care about. To solve that, we should look at our second example:

Example 2: Same file as example 1, ./biomed/rr74.txt

Our input:
```
grep -v "a\|^\s*$" ./biomed/rr74.txt
```
Our output:
```
        Introduction
        immunohistochemistry.
          Mice
          Exposure environments
          Western blotting
          with A
          260 /A
          diluted in depC H
          determined using 18 S rRNA primers/probes (Applied
          RNA.
          Immunohistochemistry
          2 -, NO
          (Ionics Instrument Business Group, Boulder, CO, USA).
          P < 0.05 is considered
        Results
          respectively;
          P < 0.001).
          Western blotting
          As shown in Fig. 2, lung eNOS protein levels were
          3.5-fold (Fig. 3).
          Immunohistochemistry
          shown).
        Discussion
        development.
        21].
        detection in the lungs of hypoxic, hypertensive mice.
        flushed with 10% O
        different species in cultures [ 31, 32, 33, 34, 35, 36, 37]
        production of NO
        piglets
        Conclusion
        considering studies using NOS-deficient mice. The present
```
Although this is still a long output because the text file itself is pretty long, we no longer have the empty spaces, or in this case "whitespace" lines showing up because of the regular expression ^\s*$ that we added after "a". You might also notice that we did "\|" after a. This is so that we can separate our arguments. We can continue to add multiple arguments by dividing them up with "\|" (backslash and the pipe character).
# '-c' option
This option returns the count (hence the c) of lines that includes the expression we input. This is a useful command-line option when we don't care about what the lines that contain our inputted text actually say and just want the number of lines that contain it.

Source: [Wikibooks](en.wikibooks.org/wiki/Grep)

Example 1: The file we will be using is ./biomed/rr74.txt

Our input:
```
grep -c "birth" ./biomed/rr74.txt
```
Our output:
```
3
```
Here, our input is "birth," so we are looking for how many lines in rr74.txt contains the word birth. Surprisingly, that word only shows up on three lines! We know this because the -c command printed 3 in our terminal.

Example 2: Here, we are still using ./biomed/rr74.txt file but now we are going to be showing you how we are also able to use the pipe character as well!

Our input:
```
grep -c "a\|e" ./biomed/rr74.txt
```
Our output:
```
371
```
Here, we are able to see the count of how many lines contain the letter a AND the letter e! Because of what we got, we see that there are 371 lines that contain these letters.
# '-w' option
The -w option is useful when you want to be specific in your search. -w allows us to search for whole words that match the search pattern (what we inputted) and not just parts of words. 

Source: ChatGPT, to explain what -w did.
        [Wikibooks](en.wikibooks.org/wiki/Grep)
        
Example 1: The file we are using is ./911report/chapter-9.txt

Our input:
```
grep -w "hijack"  ./911report/chapter-9.txt
```
Our output:
```
```
Here, we actually didn't get anything returned. Why? Because in this text file, though the word hijack does appear INSIDE of the word "hijacked", it doesn't actually return any lines because we are looking for the whole word ONLY and not parts of words. Because of this, we know that the sole word "hijack" does not appear anywhere in the file.

Example 2: The file we are using for this example is ./biomed/cc4.txt

Our input:
```
grep -w "experimental" ./biomed/cc4.txt 
```
Our output:
```
       day to day [ 11]. In sheep with experimental acute lung
          In each phase (see experimental protocol), when a
```
Here, we see that two lines were printed with the exact word "experimental." If we added a z at the end of the word, we would see no line being printed because there is not line that has "experimentalz" as its own, standalone word.

# Help Using ChatGPT(OpenAI)
With artificial intelligence starting to play a more active role in our lives, I have decided, with permission, to use it to my advantage to help me with this assignment. Here were the prompts I asked ChatGPT, which mainly asked what specific command line options did and how to return non-empty lines for the grep command in Java, alongside the answers ChatGPT gave me back.

Prompt: Is there a way to use grep and not return empty lines?
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/59e71b02-b2c1-4c3a-b2ca-749c7f3cf0b0)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/cff9dfad-be0c-45b6-a7dc-c30b9739fdee)

Prompt: Is there a way to use grep to take in multiple?
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/fe88c415-58ca-4704-9b50-49db74e9b049)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/08153ad0-f89f-43fa-96c1-1b9e79335b2c)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/9e928e60-742a-4b97-bd07-4fcbf4f5af19)

Prompt: How do I use grep to not show empty lines?
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/72ceef79-627b-42a9-881f-8c5e12872187)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/8e88fbfc-0f16-43dc-9235-163283271c48)

Prompt: Do I use single quotes or double quotes for '^$'?
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/6fd06e4f-0b51-47cb-9a84-5fe79be0ef7c)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/ac3e5ca3-1ef9-471a-ac70-7b9e1bb9042c)

Prompt: The search for empty lines isnt working.
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/31b9ccb7-3c4d-451c-b158-2b9a5480f754)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/8f581fc3-621c-4ad1-9178-3912f4a4136f)

All of the prompts above were mainly used for the second example I provided for the -v command line option since I was looking for an alternative way to use the command in a more practical way, which was to reduce the amount of lines outputted since, I think, we wouldn't want to include whitespaces and empty lines in our outputs. We also don't want unneccesarily long outputs so that's why I asked these prompts.

Prompt: What are some command line arguments for grep that are commonly useful?
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/db7664ea-1931-4d93-b40d-63885efa0580)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/71d53940-9024-44bb-a6dc-79fa05ccb8a7)

This prompt that I provided was just to find out some more command line options for grep. It gave me short descriptions of what they did which helped me choose which one I think would be useful and interesting to write with.

In summary, although I did use ChatGPT, it didn't replace my work. I mainly used it as a supplement for solving problems that would've otherwise taken me tedious web searching to find an accurate answer I needed. Most of my information about every command line option mainly came from the Wikibooks source though.
