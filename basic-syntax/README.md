# Basic Syntax

JavaScript uses a specific syntax to write code. This allows the JavaScript interpreters in web browsers to properly parse and execute that code. Like with any programming language, JavaScript interpreters can be thrown off with even the slightest mistake in syntax. A misplaced comma (`,`) or missing curly brace (`}`) can make your entire program throw an error and fail to execute. 

These sorts of issues are often the most frustrating for new developers to deal with because they are difficult to find when they happen, and they represent a failure at the "easy" part of writing code (getting the punctuation correct). It often feels like the more difficult parts of writing code **should** be the large concepts and design techniques we struggle to grasp when we first learn them. But, in fact, much of the experience that comes with coding is about being able to scan through a set of lines and quickly pick out misplaced brackets, curly braces, parentheses, and commas. 

There are some ways to help grasp syntax more easily. It's always good to use a dedicated editor that includes a "linter". A linter is a tool that helps us see issues in the code we've written, especially from a stylistic and syntactical perspective. Linters are like grammar checkers for programming languages.

Throughout this section, we will review the basics of how JavaScript gets into the web browser via HTML tags and how the fundamental building blocks of JavaScript work. We will review comments, operators, and variable declarations.

## General Syntax Rules

There are a few things to know about JavaScript that apply everywhere. Understanding how these aspects of the language work can help you avoid mistakes in the future.

### Line Endings

JavaScript uses the semicolon (`;`) to denote a line ending. Semicolons should be placed after every command in JavaScript like this:

```js
let x = 12;
```

Line endings help JavaScript interpreters parse code and make it more obvious for other developers to understand when commands begin and end. JavaScript does not recognize indentation (although you should still indent your code properly), so different developers or groups will have different ways of spacing and breaking lines. Line endings help us understand the code regardless of the stylistic choices of the developers.

### Brackets

In JavaScript, brackets (`[ ]`) are used to denote an Array and also to reference an index within an array. Here's an example:

```js
let list = ['chocolate', 'ice cream', 'cookies'];
let myFave = list[2];
```

In the example above the brackets are used to denote the Array (which is stored in a variable called `list`). The brackets are also used to reference a specific _index_ of the Array called `list`. (It's OK if this is a bit unclear; we will cover Arrays in the next section.)

### Braces
Braces (aka "curly braces") look like this: `{ }`. They denote an Object in JavaScript, and they are also used to denote code blocks. Here is an example of the two ways braces are used:

```js
let foo = {
   'name': 'Leia Organa',
   'rank': 'General'
};
```

In the example above, `foo` is an Object with two attributes: `name` and `rank`. The braces denote the contents of the Object. 

In the next example, braces are used to set off the logic for a conditional statement:

```js

if (someValue) {
    console.log('This value exists!');
} else {
    console.log('This value does not exist!');
}
```

In this example, the braces are used to denote the logic that happens for each case in the conditional. (Again, it's OK if it's fuzzy how these things work; we will cover them in an upcoming section.)

### Case Sensitivity

Throughout JavaScript, everything is case sensitive. The object `window` is not the same as the object `Window`. We must use consistent case in our naming in order to have our code work. In future sections we will talk about stylistic conventions used for naming things in our programs, and the reason those stylistic conventions exist is to allow us to more predictably name things and not have so many issues with case or formatting.

In the following example, we would see an error result because the case is inconsistent:

```js
let myValue = 42;
console.log('The meaning of life is ' + myvalue);
```

The code above would result in an "Uncaught reference error" because `myvalue` has not been declared as a variable. However, if we altered the code like this it would work:

```js
let myValue = 42;
console.log('The meaning of life is ' + myValue);
```
The result of this code would be our intended message printed out to the JavaScript console.

<div class="tip-box">
    <h3>Take heart!</h3>
    <p>
        Learning a programming language for the first time can be incredibly difficult. It's a lot like learning a foreign language for the first time. Just like we become more aware of how grammar works by studying a foreign language, we will become more aware of how "coding" works by learning to program. Programming is a combination of problem solving and then <em>encoding</em> the solution into something that a machine can interpret. 
    </p>
    <p>
        We must allow ourselves the space to learn how to express our logic through code, and we cannot make the mistake of believing that any of this stuff <em>should</em> be easy. This stuff is difficult. It is, in many ways, the culmination of thousands of years of human thought and intellectual development. Don't feel bad if it takes more than a week to learn how to do it.
    </p>
</div>
