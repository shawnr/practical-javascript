# Data Types and Structures

JavaScript is a dynamic language, which means that it determines the Data Type of a variable based on the value assigned to that variable. For example, we can assign different values to the same variable throughout our script and that variable will take on the features of different data types:

```js
var myData = "some text"; // myData is a string
myData = false; // myData is a boolean
myData = 5446; // myData is a number
myData = ['text', 42, {'name': 'Jane Doe'}]; // myData is an object
```
In the example above, we have made four different value assignments to `myData`. Each time, we have changed the Data Type for the variable. If you repeat this experiment in your web browser's JavaScript console, then you will see that you can run the `typeof()` command on this variable to find out it's value at each step:



