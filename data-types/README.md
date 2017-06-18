# Data Types and Structures

JavaScript is a dynamic language, which means that it determines the Data Type of a variable based on the value assigned to that variable. For example, we can assign different values to the same variable throughout our script and that variable will take on the features of different data types:

```js
var myData = "some text"; // myData is a string
myData = false; // myData is a boolean
myData = 5446; // myData is a number
myData = ['text', 42, {'name': 'Jane Doe'}]; // myData is an object
```
In the example above, we have made four different value assignments to `myData`. Each time, we have changed the Data Type for the variable. If you repeat this experiment in your web browser's JavaScript console, then you will see that you can run the `typeof()` command on this variable to find out it's value at each step:

![Type checking in the JS console.](/images/types-in-console.png)

## Data Structures

The primary Data Structure used in JavaScript is the Object. This is a structure that underlies virtually every aspect of JavaScript, and it's one that we use often in our regular programming work. Objects allow hierarchical relationships to be created between attributes and methods, which lets us set up conceptual frameworks to contain any idea we wish to work with in our code.

These are big ideas, so we will unpack them each on their own. Remember that if you've never learned programming before these are probably brand new ideas, and it will take some time and practice to fully wrap our heads around them. That's OK.

