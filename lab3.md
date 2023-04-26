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
  - HttpExchange t = localhost:4000//add-message?s=How are you? (the link aka the argument passed into the method)
  - URI url = add-message?s=How are you (the part of the link that is unique and is responsible for adding the word following the query)
  - String query = s=How are you? (the actual query)
  - String[] word = word[0] = s; word[1] = How are you? (separates s from the query, which is How are you)
  - message = \nHello \nHow are you? (creates a new line and then puts How are you? below Hello)
  - response = \nHello \nHow are you? (copies message)

## Part 2:

