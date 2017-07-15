# Coding Style

It's important to write clean code that we can return to at a later date, or which our collaborators can review, and make sense of. The more consistent we are with how we write our code, the easier it is to return to it later and make improvements or fixes. In all programming languages there is a notion of a standard style and approach that grows out of common usage patterns and design choices in the language itself. JavaScript, of course, is no different.

And just as each newspaper has a slightly customized style guide that governs its newsroom writers, each development group will have a somewhat unique take on things. With a language like JavaScript, which has grown and changed a lot in recent years, it can be especially confusing to read multiple style guides that come from different eras. It's crucial to consult updated material for the latest, best practices. A resource like the [JavaScript Standard Style](https://standardjs.com/rules.html) is useful, and their site contains a living guide to the latest in generally accepted JavaScript style standards.

The guidelines presented below are not exhaustive. And for every feature of JavaScript there are preferred ways to write code using those features. So we will constantly be learning more best practices and evolving our approaches a we learn more and as the language evolves. But being aware of the stylistic patterns below will help you understand the code you read more quickly and write more readable code for others.

<div class="tip-box">
<h2>Linters Are Awesome!</h2>
<p>A development in code editors over the past 10 years has been the rapid growth of "linters"&mdash;helper utilities that dynamically alert us to stylistic flaws or syntactical errors in our code. These can be thought of as a "grammar check" for code, and they work in similar ways. We can install a linter into our favorite editor (most editors support them) and they will usually underline, highlight, or mark in some way each line that causes either a stylistic warning or a syntactical error.</p>

<p>Linters are super helpful, especially as we are learning new languages. They make it easier to see the small syntax errors that so often cause new developers a lot of frustration, and they help us develop good habits writing code that meets stylistic guidelines. Look up linters for whatever editor you prefer. If you want to try an editor an linter combo, download the [Atom](https://atom.io) editor and install the [JavaScript Standard Style Linter](https://atom.io/packages/linter-js-standard) to give it a try.</p>

</div>

## Variable and Function Naming

Variables and functions should be named with "camelCase". The variable or function name should always start with a lowercase letter, and then each word in the name should be capitalized. Here are some examples:

```js

let my_var = true; // bad
let myVar = true; // good

let Foo = 42; // bad
let foo = 42; // good

function somelongname(){}; // bad
function someLongName(){}; // good

function another_long_name(){}; // bad
function anotherLongName(){}; // good
```

## Class Naming
Classes should be named in "CapitalCamelCase", which capitalizes the first letter of the name. This indicates they are class objects and helps us understand better what we're working with. Examples:

```js
class myClass {}; // bad
class MyClass {}; // good

class a_very_long_class_name {}; // bad
class AVeryLongClassName {}; // good
```

## Spacing
Consistent spacing is very useful for creating more readable code. We should put spaces after commas, around operators, and after keywords. Here are some examples:

```js
// Spacing after commas.
let myArray = [1,2,3]; // bad
let myArray = [1, 2, 3]; // good

myFunction(true,12,'Jane'); // bad
myFunction(true, 12, 'Jane'); // good

// Spacing around operators (and equals signs).
let x = 12/2; // bad
let x = 12 / 2; // good
```

## Indentation
Indentation is extremely important for writing readable code. It's nearly impossible to decipher code that is poorly indented, and bad indentation is generally seen as a huge red flag for code quality. Use 2 spaces to indent JavaScript for each code block.

```js
function capitalizetext(text){ // bad
return text.toUpperCase();
}
function capitalizeText(text){ // good
  return text.toUpperCase();
}

  if (someValue) {               // bad
console.log('This is true.');
}else{
console.log('This is not true.');
}

if (someValue) {                 // good
  console.log('This is true.');
} else {
  console.log('This is not true.');
}
```

## Code Blocks
Code blocks are defined using the curly braces (`{ }`), and they are important in JavaScript. They are used by loops, conditionals, functions, classes, and other objects in the system to define sets of logical instructions. In general, we should place the opening curly brace (`{`) on the first line opening the codeblock, and the closing curly brace (`}`) should align with that first line. Here is an example:

```js
// bad
if (x < 12) 
{
  if (x % 2 === 0) 
  {
    console.log('X is even and it is less than twelve.');
  } 
  else 
  {
    console.log('X is odd, and it is less than twelve.');
  }
} 
else 
{
  if (x % 2 === 0)
  {
    console.log('X is even and it is greater than twelve.');
  } 
  else 
  {
    console.log('X is odd, and it is greater than twelve.');
  }
}

// good
if (x < 12) {
  if (x % 2 === 0) {
    console.log('X is even and it is less than twelve.');
  } else {
    console.log('X is odd, and it is less than twelve.');
  }
} else {
  if (x % 2 === 0){
    console.log('X is even and it is greater than twelve.');
  } else {
    console.log('X is odd, and it is greater than twelve.');
  }
}
```

## And Much More

Understanding these fundamental aspects of JavaScript style will help us get started reading code and writing better coe, but we will be learning a lot more about how to write JavaScript, and as we learn new techniques we will have more use for additional style guidelines. As with almost every other form of writing, consistency is the key here, so the most important thing is for us to find a style guide we like and then stick with it. It will be much easier to accomplish that goal if we install a linter into our preferred code editor, which would be a good idea.





