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
