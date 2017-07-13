# Functions

As mentioned previously, [functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) are subroutines that can be executed whenever they are needed in our code. They are self-contained blocks of code, so they are convenient for creating "tools" or "components" that do just one thing. If we make a function that performs the "break apart a sentence into individual words and put them in an array" task, then anytime we need text capitalized in our program we can execute that function. When we execute a function's code, we use the term "call": We "call" a function, which often "returns" a result. This is how we verbalize using functions in our programs. Let's take a look at how to use them.

## Function Syntax
Functions are defined using the `function` command. This command takes a _name_, a set of _arguments_, and then defines a _code block_ that will be executed when the function is called. A standard function definition looks like this:

```js
function name(parameter){
    // this code executes
}
```
That's the basic form of a function. We call the top line of the function the "declaration" or "signature". In the example above, we have just labelled the parts. Here is an example that actually does something:

```js
function getWords(text){
    return text.split(' ');
}
```
The function above is called `getWords()`. When we write about functions, we tend to add the parentheses to indicate that the thing we're referring to is a callable function. `getWords()` takes a string of text and returns an Array of all the words in that text, separated using the space character (`' '`). The `name` of the function is `getWords`. To execute the function we would write the `name` with parentheses. Since this function also requires an `argument` (the variable specified between the parentheses after the `name` of the function), we could specify some text when we call it. The code between the curly braces is executed whenever the function is called. In this case, it is simple code, but this code could contain as many instructions as needed, and it could call other functions.

Here is what it might look like to use this function in a small program:

```js
function getWords(text){
    return text.split(' ');
}

let words = getWords("I've always been more interested in the Future than the Past.");

if (Array.isArray(words)){
    console.log(`words is an Array with length ${words.length}.`);
    for (word of words){
        console.log(word);
    }
}
```

## Function Parameters
Functions can accept parameters that are specified in the function declaration. These are named values that become variables available within the code block of the function (between the curly braces). We can write functions to generically reference the names of their parameters, and then when we call the functions in code we can send any values into those parameter "slots". 

In the example above, the function `getWords()` accepted one parameter: the `text` value. This value is given the name `text` within the function, so we are able to write the code referencing `text` and fulfill our requirements. Here is another example:

```js
function calculateArea(length, width, measure) {
    let area = length * width;
    return `${area} sq ${measure}`;
}

let boxArea = calculateArea(4,12,'feet');
console.log(boxArea);
// "48 sq feet"
```
In this example, we have a function that calculates the area of a rectangle. This formula for doing the area calculation is:  `length * width`. We have written the function to accept `length`, then `width`, which we expect to be numbers. The `calculateArea()` function also accepts a `measure` parameter, which allows for a nicer response to be crafted. Calling `calculateArea()` gives us a nicely formatted statement about the area results. 

It can be difficult to know exactly what Data Types a function wants, especially if the parameters are poorly named. To remedy this problem, it's customary to make some comment about what the function expects and what it returns:

```js
function calculateArea(length, width, measure) {
    // Calculates area of rectangle.
    // params:
    //    length - integer
    //    width - integer
    //    measure - string
    // returns:
    //    string
    
    let area = length * width;
    return `${area} sq ${measure}`;
}

let boxArea = calculateArea(4,12,'feet');
console.log(boxArea);
// "48 sq feet"
```
As we can see, this is effective at conveying the Data Types of parameters, but it takes up a lot of space in the code and is somewhat redundant. Another way we can convey this information, and gain a couple other benefits is to use Default Parameters.

## Default Parameters
[Default parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters) are parameters that are written with a default value. This allows us to better convey what Data Type each parameter should be. It's also handy to write functions that can execute with a default set of parameters most of the time, but whose parameters can be modified to fit special cases.

Here is an example of an updated `getWords()` function that uses default parameters:

```js
function getWords(text="Demo text here.", splitter=" "){
    return text.split(splitter);
}

let words = getWords();

if (Array.isArray(words)){
    console.log(`words is an Array with length ${words.length}.`);
    for (word of words){
        console.log(word);
    }
}
```
Notice that the function declaration has been updated to provide default values for each parameter. We can now just call `getWords()` and supply no text. In that case, it would process the default text string ("Demo text here."). The function is also more versatile because it uses a `splitter` param that can be changed. In most cases, we probably want to split sentences apart using spaces to get the words. For those cases, it's no more difficult to use the function.

But in cases where we want to split text apart using a different character, we can now use our same `getWords()` function:

```js
let words = getWords("bread,milk,lunch meat", ",");

if (Array.isArray(words)){
    console.log(`words is an Array with length ${words.length}.`);
    for (word of words){
        console.log(word);
    }
}
```
In this second example, we are sending in a list of comma-separated words and using the comma to perform the split. As we can see if we run the code in our JavaScript console, the modified `getWords()` function handles this special case with no trouble!

## Function Arguments
All functions also have access to an `arguments` object. [Arguments](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments) are more advanced features of JavaScript that we are not going to cover in-depth here, but they can be useful for adding extra parameters to your function calls or in situations where you can't know all of the things you will need to process (where you need to accept an arbitrary list of items, for example). Arguments can be confusing because they are not explicitly named in the function declaration. Here is an example:

```js
function makeTextList(){
    args = Array.from(arguments);
    return args.join(',');
}

let shoppingList = makeTextList('bread','milk','lunch meat');
console.log(shoppingList);
// "bread,milk,lunch meat"
```
When using arguments in a function, keep in mind that the `arguments` object is not a standard Array, but we can use the `Array.from()` function to transform the `arguments` object into a standard Array. There are many more great ways to use arguments, but they are a bit beyond where we are right now. 

## Returning Data From Functions
Once we've completed some calculation or processing in a function, we often want to send some data back to the main logic of our program. To do this, we use the `return` statement.

In each example above we've seen how we can return data to whatever command called the function. Once that data has been returned, it can then be used by subsequent instructions. This is a very common pattern for using functions in code. Here is an example:

```js
function calculateTax(amount = 9.42, tax = 0.065){
    return amount * (1 + tax);
}

let subtotal = 12.57;
let total = calculateTax(subtotal);
```
In this example, we have a simple function that calculates tax. We can use this function whenever we need it, and it helps us generate the value for the `total` variable. The `total` variable might be used in many places: in a template to render it for the user, stored in a database, emailed to an email receipt, etc. 

In the case above, the `return` statement is returning the results of the calculation directly. It would be possible to store those results and return the variable where they were stored like this:

```js
function calculateTax(amount = 9.42, tax = 0.065){
    let taxedAmount = amount * (1 + tax);
    return taxedAmount;
}

let subtotal = 12.57;
let total = calculateTax(subtotal);
```
We could even be building up a much more complex Object or Array of values that could be returned and stored in the `total` variable. Sometimes this is needed when we have to track additional metadata (such as what tax rate was applied, or what time the transaction was processed). 

Using functions to process information and return data is a powerful tool for building complex programs. 

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.



{% exercise %}
Define a function that would uppercase a String. You can use the <code>String.toUpperCase()</code> to capitalize a String. An example is shown in the starter code. Package that example into a function that will take a parameter called <code>text</code> and return the uppercase version of it.

{% initial %}
// Example of using `String.toUppercase()`
let example = "abcd";
console.log("Uppercased result: " + example.toUpperCase());

// Function goes here
var myText = capitalizeText("http");

{% solution %}
function capitalizeText(text){
    return text.toUpperCase();
}
var myText = capitalizeText("http");


{% validation %}
assert(myText=="HTTP", "Incorrect.");

{% endexercise %}

{% exercise %}
Define a function that utilizes default parameters to produce the default message "Hello, world!"

{% initial %}
// Function goes here
var greeting = sayHello();

{% solution %}
function sayHello(salutation="Hello"){
    return `${salutation}, world!`;
}
var greeting = sayHello();


{% validation %}
assert(greeting==="Hello, world!", "Incorrect. Please make sure text of your greeting is correct.");

{% endexercise %}



