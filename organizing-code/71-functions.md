# Functions

As mentioned previously, [functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) are subroutines that can be executed whenever they are needed in our code. They are self-contained blocks of code, so they are convenient for creating "tools" or "components" that do just one thing. If we make a function that performs the "break apart a sentence into individual words and put them in an array" task, then anytime we need text capitalized in our program we can execute that function. When we execute a function's code, we use the term "call": We "call" a function, which often "returns" a result. This is how we verbalize using functions in our programs. Let's take a look at how to use them.

## Function Syntax
Functions are defined using the `function` command. This command takes a _name_, a set of _arguments_, and then defines a _code block_ that will be executed when the function is called. A standard function definition looks like this:

```js
function name(argument){
    // this code executes
}
```
That's the basic form of a function. Here is an example that actually does something:

```js
function getWords(text){
    return text.split(' ');
}
```
The function above is called `getWords()`. When we write about functions, we tend to add the parentheses to indicate that the thing we're referring to is a callable function. `getWords()` takes a string of text and returns an Array of all the words in that text, separated using the space character (`' '`). The `name` of the function is `getWords`. To execute the function we would write the `name` with parentheses. Since this function also requires an `argument` (the variable specified between the parentheses after the `name` of the function), we could specify some text when we call it. 

Here is what it might look like to use this function in a small program:

```js
function getWords(text){
    return text.split(' ');
}

let words = getWords("I've always been more interested in the Future than the Past.");

if (Array.isArray(words)){
    console.log(`words is an Array with length ${words.length}.`);
}
```

## Function Arguments

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

