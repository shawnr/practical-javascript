# Data Types and Structures

JavaScript is a dynamic language, which means that it determines the Data Type of a variable based on the value assigned to that variable. For example, we can assign different values to the same variable throughout our script and that variable will take on the features of different data types:

```js
let myData = "some text"; // myData is a string
myData = false; // myData is a boolean
myData = 5446; // myData is a number
myData = ['text', 42, {'name': 'Jane Doe'}]; // myData is an object
```
In the example above, we have made four different value assignments to `myData`. Each time, we have changed the Data Type for the variable. If you repeat this experiment in your web browser's JavaScript console, then you will see that you can run the `typeof()` command on this variable to find out it's value at each step:

![Type checking in the JS console.](/images/types-in-console.png)

Anytime in your code we can check the type of a value using the `typeof()` command. This allows us to make better decisions, prevent errors, and provide more functionality to our users. 

## Data Structures

The primary Data Structure used in JavaScript is the Object. This is a structure that underlies virtually every aspect of JavaScript, and it's one that we use often in our regular programming work. Objects allow hierarchical relationships to be created between attributes and methods, which lets us set up conceptual frameworks to contain any idea we wish to work with in our code.

These are big ideas, so we will unpack them each on their own. Remember that if you've never learned programming before these are probably brand new ideas, and it will take some time and practice to fully wrap our heads around them. That's OK.

<div class="tip-box">

<h3>Duck Typing</h3>

<p>JavaScript's dynamic typing is a concept that is sometimes hard to grasp. It is probably most accurately called <a href="https://en.wikipedia.org/wiki/Late_binding">dynamic (or "late") binding</a>, which is not a particularly friendly term. Computer scientists and developers have discussed JavaScript's typing system at great length, largely due to the fact that the method provides both a great deal of flexibility and a not-inconsequential amount of variability. Sometimes, in JavaScript you have to try the code to know for sure what you're going to get, and that unpredictability can sometimes lead to breakage in software.</p>

<p>A common, <a href="https://ericlippert.com/2014/01/02/what-is-duck-typing/">not entirely accurate</a>, but much more friendly way to think about JavaScript's typing system is with the term <a href="https://en.wikipedia.org/wiki/Duck_typing">"Duck Typing"</a>. This term refers to the fact that JavaScript does not actually <em>care</em> what the type of a value is, only that it has all of the features needed by your code at the moment.</p>

<p>For example, if we are trying to perform a `split()` on some text (to break apart words or letters), the JavaScript interpreter only looks for that `split()` method to exist on our variable. If the variable is, indeed, currently set to a type that supports `split()` then the code executes properly. If not, then an error is raised.</p>

<p>Another way to express this is like so: JavaScript doesn't care whether it's dealing with a Duck. If it quacks like a duck, walks like a duck, flies like a duck, and swims like a duck, then it's a duck.</p>

</div>