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
![image](https://user-images.githubusercontent.com/130111913/230806825-5f3f3ec9-dedd-4785-8e11-c10d018e7988.png)

If all your commands work, you've done it! To log out, do ```CTRL``` + ```D``` and then type ```exit``` in your terminal.
