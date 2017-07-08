# Variables

In any programming language, data and discrete blocks of code can be labeled for reference throughout the program. We call these references "variables". Variables can have different values at different points in the code execution. For example, a variable named `counter` might be initialized to zero, but its value would likely be changed throughout the execution of the code as different logic is processed. It might be counting all sorts of objects or actions in the program.

When we create a variable, we call that "declaring" the variable. At the same time we declare a variable, we could also initialize the value of that variable to something. If we do not initialize the value of the variable to something, then JavaScript assigns the value `undefined` to that variable. 

There are three ways to declare a variable in JavaScript: `var`, `let`, and `const`.

## `var`
The generic way to declare a variable in JavaScript is to use the `var` command. This creates a variable that can be accessed in a variety of different ways. It is close to being a "global" variable, although that is something unique in JavaScript (and something we cover in a future section of this book).

Here is an example of declaring a variable using `var`:

```js
var foo = "some value";
```

<div class="tip-box">

<h3>The Old Way: <code>var</code></h3>

<p>Due to the way that scope worked in JavaScript prior to ECMAScript 6, <code>var</code> was the old way of making local variables. Unfortunately, the <code>var</code> command does not actually make a variable local in the way most developers expect, and it has been replaced with the <code>let</code> command. The <code>var</code> command still works as it always has, but modern JavaScript should avoid using it as much as possible.</p>

</div>



## `let`
Most of the time in JavaScript, we want to control the "scope" of our variables. Scope is a term that we will dig into much more deeply later in this book, but for now it's worthwhile to understand that the `let` command allows us to create a "local" variable, which can only be used within its own code block. Here is an example:

```js
let bar = "another value";
```

## `const`
Most programming languages have a notion of "constant" variables, which are variables whose value cannot be changed during the execution of the program. Once we declare and initialize a variable with the `const` command we cannot change the value of that variable. This is useful for setting up parameters or preferences for our code. Here is an example:

```js
const userID = 42;
```

## Declaring and Initializing Variables
When we write code, we want to make it as clear as possible for ourselves (or our collaborators) to understand when we return to it. Sometimes this is helped by declaring variables at the top of a file even though we might not initialize them until later. It's not uncommon to see a list of variable declarations like this at the top of a file:

```js
var foo,
    bar,
    baz;
    
const apiDOMAIN = "api.example.com"; 
const apiPort = 8080; 
const apiVersion = "1.3"; 

const apiBasePath = `http://${apiURL}:${apiPort}/${apiVersion}/`;
```

In the example above, we have declared three variables for use later: `foo`, `bar`, and `baz`. At the time they are declared, they are not initialized to any value. A variable that is declared without a value automatically has the value `undefined` in JavaScript.

The other variables we declare are used to assemble the `apiBasePath` value. These values would likely be derived from inspecting some other aspect of the environment, and that information would be stored in constants so they cannot be altered during runtime. This insures that these values will not accidentally get overwritten with bad information.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.

{% exercise %}
Define a variable `x` equal to 10.

{% initial %}
let x =

{% solution %}
let x = 10;

{% validation %}
assert(x == 10);

{% endexercise %}

{% exercise %}
Define a variable `x`, but do not initialize it.

{% initial %}


{% solution %}
let x;

{% validation %}
assert(x == undefined);

{% endexercise %}
