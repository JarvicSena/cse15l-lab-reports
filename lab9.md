# Lab 9 (Report 5)
## Part 1 (EdStem Post)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/d545a3a0-967a-489c-a87a-91b7e542b85c)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/0f7ca24d-e889-4c0f-aa4c-6d2d2d8316bc)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/3ad625a4-ad8c-4da9-8a7c-6c71076052f0)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/2f99dd96-6d12-4719-b08f-33ff819b8fe4)

**TA Response**
Actually, your error is how the for loop is iterating, but it's in your calculateAverage method. Have you checked the condition of your loop? Again, this is in the calculateAverage method, and not in main.

**Output after TA Response**
```
$ ./calculate.sh
Compilation successful. Running the program...
Enter the number of elements in the array: 5
Enter the elements of the array:
10
20
30
40
50
Average: 30.0
```
I changed the condition to be i < numbers.length rather than i <= numbers.length. The bug was that i <= numbers.length led to i incrementing to 5, which is out of bounds in our case since  the index of the last number in the array is 4. 
**File and Directory Structure Needed**
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/11c4251a-b2e3-499a-95ea-4b46b783c1cc)
Make sure that the java file and script file is in the same directory. In this case, we are in the 15L directory (folder) that I have in my computer and created the files there. This is so that when you run the script, it knows what the java file you are talking about is.

**Before Bug Fix**

*Java File*
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/8d8ed198-ed6b-450c-801e-3220d8cf77ac)
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/0a00bc8f-e959-49cd-8909-021e4cd8ca44)

*bash script file*
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/1370c7f9-c7d7-4045-9a6b-0273a07f698a)

**Failure-inducing Input**
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/3d642b1b-725e-4eec-8d95-9f0d98d063cc)

**How To Fix The Bug**
We do what the student did! We change the for loop condition in the calculateAverage method to *i < numbers.length* instead of *i <= numbers.length.* It is a subtle difference but that one difference causes the error!
![image](https://github.com/JarvicSena/cse15l-lab-reports/assets/130111913/f73bf31b-1195-4dde-93b0-f990ce4e92ea)

## Part 2: Reflection
What I learned from the second half of the quarter that I found interesting was the vim lab, trying to time ourselves and using some shortcuts in search mode to jump around a file quickly. I think it is interesting because while, yes, it can be confusing at times to navigate, I can imagine that with practice, you can get really fast with it which helps us make changes from our terminal to our code quickly if needed without needing a mouse. It can be useful, for example, if you are on a laptop since the scroll on some laptops are pretty slow or bad. But in general I think that vim is a good file editor.
