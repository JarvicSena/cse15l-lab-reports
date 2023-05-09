# Lab 3
## Part 1:

Here's my code for ```StringServer```:
![image](https://user-images.githubusercontent.com/130111913/234527371-ebd170fb-4b5a-4a8d-91cc-04fc5c63deb4.png)
![image](https://user-images.githubusercontent.com/130111913/234527494-ecb04c56-cc9f-4e6d-961e-01332c0dcf95.png)

Here's two uses of ```/add-message```:
![image](https://user-images.githubusercontent.com/130111913/234532743-795f9f4f-e20e-4237-8797-e5048bad77de.png)
- The method ```handle``` in the class ```MyHandler``` is being called.
- The relevant argument to this method is ```t```, which is the link typed and is of type ```HttpExchange```
- The values of the relevant fiels of the class are:
  - HttpExchange t = localhost:4000//add-message?s=Hello (the link aka the argument passed into the method)
  - URI url = add-message?s=Hello (the part of the link that is unique and is responsible for adding the word following the query)
  - String query = s=Hello (the actual query)
  - String[] word = word[0] = s; word[1] = Hello (separates s from the query, which is Hello)
  - message = \nHello (creates a new line and then puts Hello)
  - response = \nHello (copies message)
![image](https://user-images.githubusercontent.com/130111913/234532850-eb3064b4-64f7-4410-a41a-42072753202a.png)
- The method ```handle``` in the class ```MyHandler``` is being called.
- The relevant argument to this method is ```t```, which is the link typed and is of type ```HttpExchange```
- The values of the relevant fiels of the class are:
  - HttpExchange t = localhost:4000//add-message?s=How are you? (the link aka the argument passed into the method. This part changes because the query is different)
  - URI url = add-message?s=How are you (the part of the link that is unique and is responsible for adding the word following the query. This also changes because of the query)
  - String query = s=How are you? (the actual query, which changes every time you input something after s=)
  - String[] word = word[0] = s; word[1] = How are you? (separates s from the query, which is How are you. word[0] is always 0 but word[1] is the query so it changes after every call of the method)
  - message = \nHello \nHow are you? (creates a new line and then puts How are you? below Hello. This changes because you are adding a new word since you used /add-message a second time)
  - response = \nHello \nHow are you? (copies message. does't change the value of message but it is different from the first response)

## Part 2:

The bug I am choosing from lab 3 is from the method ```reverseInPlace()```

Here's a failure inducing input, which is an array with more than one element: 
```
 @Test
  public void testReverseInPlace1() {
    int[] input2 = {2, 4, 6};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{6, 4, 2}, input2);
  }
  ```
Here's another, with two inputs:
```
@Test
 public void testReverseInPlace2() {
    int[] input3 = {4, 12};
    ArrayExamples.reverseInPlace(input3);
    assertArrayEquals(new int[]{12, 4}, input3);
  }
```

Here's an input that doesn't cause an error, because the reverse method doesn't actually reverse an array with just one element:
```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
  ```
Here's the symptoms:
![image](https://user-images.githubusercontent.com/130111913/236987465-be319898-7a80-4d93-a9c7-2f4d8ad487b0.png)

Here's what the faulty code with the bug looked like before I fixed it:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
Essentially, the bug is caused by the fact that once the array reverses once it reaches halfway, it reverses itself back because it loops all the way through the whole array. 
here's what the new code after I debugged it:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```
I made it so that the arr.length part is now arr.length/2. I also added a temp variable to store the variable to be switched and used that temp variable to assign the
stored value into where it should be, which is the “mirror index”. The mirror index would be the index reverse from the start. For example, arr[0]'s mirror index is
arr[arr.length - 0 - 1], aka the last index of the array. This fixes the bug because now that the array only loops through the first half of the array, it doesn't put
things back to where they originally were. The temp variable also allows us to remember the value of the array we would like to switch easily.

## Part 3:
One thing I learned from week 2 and 3 was that URI's are not URL's. URI's contain the URL and is the string that *indentifies* a link and the URL is the actual location 
of the link. URL's are what we typically know as the address bars at the top of the website we are seeing. URI's are something we don't normally see and if we saw 
one that didn't contain a URL, we wouldn't know what it was. Here's an example of a URI: urn:isbn:0-476-27557-4. Here's an exmaple of a URL: https://google.com.
I also learned that you can add paths and behaviors, if your code allows it, that allows you to add strings into a server and display it on a website and also search for strings in a server that displays on a website, which is essentially what we did with StringServer in this lab.
