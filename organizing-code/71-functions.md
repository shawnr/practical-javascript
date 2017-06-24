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

## Returning Data From Functions


{% exercise %}
Define an a `for` loop that would double (multiply times two) `foo` 12 times.

{% initial %}
var foo = 2;
for ( ){
    
}

{% solution %}
var foo = 2;
for (let i=0; i<12; i++){
    foo = foo * 2;
    console.log(`Foo equals ${foo}.`);
}

{% validation %}
assert(foo==8192, "Incorrect.");

{% endexercise %}

