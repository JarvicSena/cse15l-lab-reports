# How To Log Into Your Course-Specific Account on ieng6 (Remote Connect)
Today, we're going to help you log onto your account on ieng6 so you can connect to remote computers and get some code done!

## Part 1: Installing VScode
To install VScode, simply type VScode in Google and click on the first link. The website should be [code.visualcode.com](https://code.visualstudio.com/). If you have Mac, download the Mac version and the Windows version if you have a Windows computer. Of course, download the Linux version if you're on Linux. Here's what it should looks like when you open VScode, though the colors might look different due to your settings.
![image](https://user-images.githubusercontent.com/130111913/230564006-93740071-18ea-42ca-b0d5-06c6639bc2bb.png)

## Part 2: Remotely Connecting
Now that you have VScode, if you have windows, you want to download git for windows. Click this [link](https://gitforwindows.org/) to download git. 
1. To remote connect, open the terminal by pressing and holding ```CTRL``` + ```'``` (the top left corner of your keyboard) or clicking Terminal in the top left and clicking New Terminal.
2. Open the command palette using ```CTRL``` + ```Shift``` + ```P```. 
*for the following steps, you will have to do them all at once or else you'll have to start from Step 3 (unless you have a second tab).
3. Type - Select Default Profile
4. Select Git Bash
5. Click on the + in the Terminal window. The terminal should now be a Git Bash terminal. You should also be able to toggle between different terminals from the drop down menu
![image](https://user-images.githubusercontent.com/130111913/230569822-5345f8ae-9d8b-43df-829a-40889580f45a.png)
![image](https://user-images.githubusercontent.com/130111913/230570480-6ab224d5-78f3-4701-a42f-ea80db8dd78b.png)
6. To use ```ssh```, type (your username here)@ieng6.ucsd.edu. You should get a prompt asking you something like "Are you sure you want to keep connecting  (yes/no/[fingerprint])? Type yes and then type your password. *you shouldn't be able to see your password while you enter it so be sure you're typing it corrently.* You should end up with something like this:
![image](https://user-images.githubusercontent.com/130111913/230802157-d4bb04fb-377c-4b6e-ba38-1639c0b8890e.png)

## Part 3: Running Some Commands
Now that you are logged in remotely and ssh'd, you can now run some commands on the remote computer. You can run commands on the remote computer by using *cd*, *ls*, *pwd*, *mkdir*, and *cp* in VScode or on your computer's command prompt. Here's what I ran. You can do the same to see if it works!

![image](https://user-images.githubusercontent.com/130111913/230806813-18c91c49-9daf-4629-93cb-7249467c618a.png)
Above, I ran *cat* <file1> ... which prints out the contents of the file I inputted, which is "Hello!" (without quotes). In this case, it looked at the helo.txt file inside the cs15lsp23 folder and printed its contents.
 
![image](https://user-images.githubusercontent.com/130111913/234133302-ede80201-f9af-4611-9352-4e42354ad26a.png)
Here, I used *pwd*, or, "print working directory" which displays the current working directory I am im which, in this case, is /home/linux/ieng6/oce/5k/jsenatin.

![image](https://user-images.githubusercontent.com/130111913/234134082-3e2b70fe-caf6-4fc0-9413-7bd15b802224.png)
Here, I ran both cd ~, which changes the directory to the home directory. I then just typed cd with nothing after, which doesn't change the directory technically even though *cd* means "change directory" because there's nothin after it. It is important to note that even though nothing is outputted into the terminal, the command did still run since we are allowed to type more commands after and no errors were thrown.

![image](https://user-images.githubusercontent.com/130111913/234134776-ac8c3504-5ff4-4d5a-8edc-bce372ccac4a.png)
Lastly, I ran ls -a and ls -lat. The *ls* command, aka the "List" command, lists files and folders int he given path. But because I used -a the first time, it lists *all* the files, including hidden ones. The second time, when I ran ls -lat, it also lists the files but now in a "long list style" (the l part after the dash), all the files (a), and the time in which they were edited in order from most recent to least recent from top to bottom (t). 

  
To summarize, I ran *cat <filename>*, *pwd*, cd ~, *cd*, *ls -a*, and *ls -lat*. Of course, there are plenty of other commands and a lot more combinations of arguments you can pass in after them but these are some of the ones I tried. You can try others to ensure everything works and all your files are where they're supposed to be. 
  
If all your commands work, you've done it! To log out, do ```CTRL``` + ```D``` and then type ```exit``` in your terminal.
