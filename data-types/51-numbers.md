# Numbers

Most programming languages make a division between an integer and a decimal. JavaScript does not make any distinction between the two. JavaScript has only one numeric Data Type, called Number. If a variable is given a numeric value, then it will be of the type "number":

```js
let x = 12;
if (typeof(x) === "number"){
    // This code will execute because 12 is a value of the type "number".
    console.log('x is a number!');
}
```

We could change the value of `x` to `3.14` and the conditional above would still evaluate to `true` in the same way because as far as JavaScript is concerned there is no difference between a whole number and a number with a decimal point.

It is possible to determine whether or not a Number is an integer using a tool provided by the `Number` object. consider the following code:

```js
let x = 12;
if (Number.isSafeInteger(x)){
    // This code will execute because x is currently set to an integer value.
    console.log('x is an integer!');
}
x = 3.14; // Change x to a decimal number.
if (Number.isSafeInteger(x)){
    // This code will not execute because x is currently set to a decimal value.
}
```
The `Number.isSafeInteger()` function can be used to determine if a number is an integer or not. If it is an integer, the function will return `true`. If it is not an integer, then it will return `false`. In the cases where differentiation between types of numbers matters, this is a helpful tool.

<div class="tip-box">
    <h2>Unexpected Math</h2>
    <p>JavaScript does not have a way of restricting "floating point" or "decimal" numbers to a specific number of places. We can use methods like <code><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed">Number.toFixed()</a></code> to round off at a specific decimal point, but we can always expect to see weird things like this:</p>
    <pre>
let total = 0.10 + 0.20; // expected result is 0.3 (or maybe 0.30)  
console.log(`Actual value of total is: ${total}`); // prints 0.30000000000000004 to the console.
    </pre>
    <p>This all stems from the fact that numbers with decimal points in JavaScript are all treated as "floating point" numbers, which is not the precise "decimal" numbers we are used to dealing with in our finances or other aspects of our daily lives. We won't dive into what makes "floating point" numbers work, but we can recognize and anticipate that we might encounter trouble working with decimal numbers in JavaScript when dealing with decimals. If we are working on certain types of applications, we may need to explore some different methods for working around the unexpected results of floating point math.</p>
    <p>The savvy developer will search around for the latest <a href="https://modernweb.com/what-every-javascript-developer-should-know-about-floating-points/">articles</a>, <a href="http://floating-point-gui.de/languages/javascript/">cheatsheets</a>, and <a href="https://stackoverflow.com/questions/1458633/how-to-deal-with-floating-point-number-precision-in-javascript">examples</a> for dealing with floating point issues in their code.</p>
</div>


## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Define a variable `x` equal to an integer.

{% initial %}
let x =

{% solution %}
let x = 10;

{% validation %}
assert(Number.isSafeInteger(x));

{% endexercise %}

{% exercise %}
Define a variable `x` equal to a decimal.

{% initial %}
let x =

{% solution %}
let x = 3.14;

{% validation %}
assert(!Number.isSafeInteger(x));

{% endexercise %}
