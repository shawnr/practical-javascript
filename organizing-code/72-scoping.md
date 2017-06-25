# Scope and Scoping

Some commands we've used throughout this book without really explaining why are the `var` and `let` commands, which are used to declare a variable. We know they indicate that a new variable has been created, but we have not yet discussed how these commands are different, or what those differences mean for our code. In this section we will cover these differences and how to use them in a program.

## Scope
In programming languages there is generally a notion of "scope". The [scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope) is a term used to describe the current context of the code: all of the variables, functions, objects, etc. that are known to the programming language interpreter at the time of execution. Take the following snippet of JavaScript as an example:

```js
var foo = "Hello, world!";
var bar = 42;

function baz(){
    console.log("The question of whether a computer can think is no more interesting than the question of whether a submarine can swim.");
}

var quote = baz();
console.log(`Foo: ${foo}`);
console.log(`Bar: ${bar}`);
console.log(`Quote: ${quote}`);
```
In the example above, the scope of this script includes all of the globally available objects available in JavaScript (objects like `Number` and `Object` and `for` and `if`, to name a few). The scope also includes three code objects that we have defined: `foo`, `bar`, and `baz()`. Although `foo` is a String, `bar` is a Number, and `baz()` is a Function, each of them is "known" to the JavaScript interpreter as it executes these lines. When we set `quote` equal to `baz()`, the interpreter understands which function we are calling because everything is accessible within the same scope.

There are, however, situations where variables or functions may not be known to all scopes. Sometimes we want to make variables exclusive to certain parts of our code. Each time we declare a variable, we must make a choice about whether we want that variable to be "global" or "local". 

<div class="tip-box">

<h3>Hoisting in JavaScript</h3>

<p>A somewhat unique feature in JavaScript is the notion of hoisting.</p>

</div>





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

