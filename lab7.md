## Lab Report 7 (Report 4)
# Using Vim
After setting up your ieng6 login and making sure you don't have the repository in github or in your ieng6 account and forking a new unedited one, you can now time yourself on the following steps:

### 1. Log in to ing6 (you shouldn't need to input your password now):
```
Keys pressed: <Ctrl>+<R> <up> <Enter> The command was one up in the search history, so I pressed the up arrow once and then enter to run it.
```
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/7eb2e36f-2108-4350-8b42-befeb213967d)
  
### 2. Clone your fork of the repository from your GitHub account:
``` 
Keys pressed: <g> <i> <t> <Space> <c> <l> <o> <n> <e> <Space> <Ctrl>+<P> I pasted the ssh link of the cloned repository into the terminal to clone it.
```
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/76816410-614e-42a1-85c4-fb7a35dfb0cd)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/fe92fccf-ca65-46f1-872e-a9ec4f3cea1c)

Note that the link should be the same as the one you just copied from the GitHub site. ALSO note that I am copying the link under SSH!

### 3. Run the tests, demonstrating that they fail.
``` 
Keys pressed: <c> <d> <Space> <l> <a> <b> <7> <Enter> <Ctrl>+<R> <up> <up> <up> <up> <up> <up> <up> <up> <up> <up> <Ctrl>+<R> <up> <up> <up> <up> <up> <up> <up> <up> <up> <up>
I first changed the directory into lab7 to ensure I'm in our now cloned repository. Then I found that the command to compile the tests was 10 up in the search history so I pressed the pressed up 10 times and then enter to run it. Then I found that the command to run it was also 10 up in the search history so I pressed up 10 times and then enter to run that. 
```
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/1abe4746-0a95-4430-a182-1ea6a52314ab)
Here, we see that we are failing, so we know there is something we need to fix. That is where Vim comes in handy.

### 4. Edit the code file **ListExamples.java** to fix the failing test (as a reminder, the error in the code is just that **index1** is used instead of **index2** in the final loop in **merge**)
```
Keys pressed: <v> <i> <m> <Space> <L> <i> <s> <t> <E> <x> <a> <m> <p> <l> <e> <s> <.> <j> <a> <v> <a> <Enter> </> <c> <h> <a> <n> <g> <e> <Enter> <j> <l> <l> <r> <2> <Esc> <:> <w> <q> <Enter>
Here, we use the vim command to access ListExamples.java, which is the file we want to edit. Then, we do / to search for a word near the one we want to edit, in this case, change. Then we press enter and then using the movement keys (h,j,k, and/or l) to put our cursor on top on the number 1 that we want to change. Then, by typing r we get into a "replace" mode and then type the number 2, replacing 1 into 2. After, we press escape to, well, escape, and then :wq to save our changes and quit out of Vim.
```
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/201ab5e6-5b98-427b-9905-e91bff99bf79)
Here's the edited image, where index1 is now edited to index2 (if you follow the key presses after getting into the file using vim)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/5da5617e-1276-4659-b8c1-3a530d90d7ae)
Here's what it looks like once you editted and saved the file (:wq). You go back to the terminal.

### 6. Run the tests, demonstrating that they now succeed.
```
Keys pressed: <Ctrl>+<R> <up> <up> <up> <Enter> <Ctrl>+<R> <up> <up> <up> <Enter>
The command to compile the files was 3 up the search history, so I pressed up 3 times and pressed enter. Then, the command to run was 3 up the search history, so I also pressed up 3 times and then press entered.
```
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/38ef2da7-c7ae-42cb-8eea-8fc5fecc886e)

### 7. Commit and push the resulting change to your GitHub account.
```
Keys pressed: <g> <i> <t> <a> <d> <d> <"> <L> <i> <s> <t> <Space> <E> <x> <a> <m> <p> <l> <e> <s> <.> <j> <a> <v> <a> <"> <Enter> <g> <i> <t> <c> <o> <m> <m> <i> <t> <-> <m> <"> <U> <p> <d> <a> <t> <e> <d> <"> <Enter> <g> <i> <t> <Space> <p> <u> <s> <h> <Space> <o> <r> <i> <g> <i> <n> <Space> <m> <a> <i> <n> <Enter>
Here, we used a sequence of git commands: git add, git commit, and git push to commit and push our changes. We first did git add "ListExamples.java" since that is the file we edited and want to push. Then we do git commit -m "Updated" to write a message into GitHub saying that we "Updated" this file. Lastly, to push all of this into our account, we do git push origin main to push into our account.
```
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/4bae9a65-bab6-41b7-954c-7c1353412eba)
Above is what happened in our terminal.
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/c0631fac-62da-4926-a4e5-36ff3af42fec)
Now, here's what we should see inside the lab7 repository. "Updated" is our message right next to ListExamples.java

Lastly, if you click into ListExamples.java in GitHub and scroll down the file, you should see that index2 is now there, rather than input1.
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/c411eba3-3b33-4935-96a1-695e9d15bae3)

We fixed the bug!
If you started a timer, now would be the time to stop it. This was the fastest way I was able to do it but I'm sure with enough practice, you can get even faster. Have fun!
