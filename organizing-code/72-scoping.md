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

## Global Variables: `var`
In ECMAScript 6 (the latest standard for JavaScript), there are two types of variables: Global and local. Global variables in JavaScript are declared with the `var` command:

```js
function echoNum(){
    myNum = 42
    console.log(`myNum: ${myNum}`);
}

echoNum();
var foo = myNum;
console.log(`foo: ${foo}`);
```
In the code above, `myNum` is declared as a global variable within the `echoNum()` function. This means that we can reference `myNum` from outside the function where it is declared (and assign its value to `foo`).

The `var` command used to be the standard way of declaring a variable in a JavaScript program. There is a distinction between variables that are truly global (declared with no `var`, `let`, or `const` command) and variables declared with `var`, but we won't be getting into that at this point. In most cases, `var` effectively creates a variable that is usable by all parts of your program. **NOTE:** At this point in JavaScript history, it's preferred to use local variables declared with `let` (see below) over global variables or variables declared with `var`.

Variables declared with the `var` command should be treated as global variables (they aren't _exactly_ global variables, but for now that's the safest way to treat them), which means their usage should be limited. In general we try to declare as few global variables as possible. This is for a few reasons, but primary among them are these three: 

1. Global variables take up a name that cannot be used anywhere else in our code. Having global variables with generic names like `counter` or `item` would be difficult to accommodate, since we often want to use those words in different contexts and not have our data or operations get mixed up.
2. The larger the scope becomes for any given piece of code, the longer it takes to interpret. By controlling how many code objects we load into our scope we can make our code execute more quickly.
3. The more objects we have floating around in our global scope, the more chance there is for error. Operations can get mixed up. Data can get mangled. Generally "bad craziness" might ensue.

## Local Variables: `let`

In most of our coding tasks, we attempt to keep our variables and functions local to small pieces of code. The `let` command allows us to declare a variable that only exists in the code block where it is declared and any code blocks contained within (children of the original code block). Here's an example:

```js
function echoNum(){
    let myNum = 42;
    console.log(`myNum can be referenced inside the function: ${myNum}`);
    if (myNum === 42){
        console.log(`myNum can be referenced in this conditional: ${myNum}`);
        let foo = "Even more local.";
        console.log(`foo has been declared and scoped to exist only within this conditional: ${foo}`);
    }
    console.log(`foo cannot be referenced outside of the conditional where it is declared: ${foo}`);
}
console.log(`myNum CANNOT be referenced outside the function: ${myNum}`);
```
In this example, we see that `myNum` is declared inside of `echoNum()`, but it is declared with the `let` command. This means that `myNum` only exists inside of `echoNum()` and any code blocks contained within `echoNum()`. The conditional inside of `echoNum()` is another code block (indicated by the curly braces), and it can reference `myNum`. Within the conditional codeblock the variable `foo` is declared. This variable only exists within the conditional statement. It cannot be referenced outside of the conditional at all.

This example shows several ways in which `let` restricts the availability of local variables. Local variables are available inside their own scope (code block) and any "child" scopes (code blocks). 

It's useful to be able to make local variables with `let` because we often need to make quick variables that perform similar tasks within different code blocks. For example, we may wish to use variables to control a loop (e.g. `counter`, `index`, `item`) or to help with a conditional (e.g. `isSaved`, `isDirty`) and not have those values persist outside of their specific code block. We could use these variable names in multiple contexts, so keeping them local to each one is crucial.

<div class="tip-box">

<h3>Hoisting in JavaScript</h3>

<p>A somewhat unique quality of JavaScript is the notion of "hoisting". A variable declared with <code>var</code> or function may be used before it is declared, as long as it is declared somewhere later in the code. This can lead to situations where a variable may be referenced or a function may be invoked on a line preceding the actual declaration of that variable or function. In general, it's best to avoid reliance on this quality because it can lead to writing confusing code that is difficult for other developers to read and understand.</p>
<p>This is not an actual feature of JavaScript; it is a byproduct of the way that JavaScript is interpreted and executed. When a JavaScript program is interpreted, the code is reviewed and all objects that are defined are kept in memory. This allows the interpreter to review the code, find the important objects, and then understand references to those objects, even if the references in the code are made on lines preceding the object declarations. Although it's a reliable effect of interpretation,  it's still not recommended to make a habit of using functions or variables before you have declared them. In fact, the standard practice is to declare all variables at the beginning of a code block or file, and to define functions in some location within our code that makes sense.</p>

</div>




