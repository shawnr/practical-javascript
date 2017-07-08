# Conditionals

[Conditionals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling#Conditional_statements) are sets of code instructions that execute if a given assertion is `true`. These are commonly expressed as "if/then" statements, and they are essential to controlling logical flow. 

## Basic Conditional Syntax
We often call conditionals "if statements" because in most programming languages the keyword "if" is used. In JavaScript, we write a conditional statement like so:

```js
if (true) {
    // code here executes when the condition is true
    console.log('It's true!');
}
```
This is a simple statement that checks if an assertion is true. In this case, since the assertion is simply `true` it will always execute the code. But we can do more with conditionals. Here is a more complex example:

```js
let foo = 12;
let bar = 42;

if (foo > bar ) {
    // In this example, this `foo` is less than `bar`, so this code will not execute.
    console.log('Foo is bigger.');
} else {
    // Since `bar` is greater than `foo`, this code will execute.
    console.log('Bar is bigger.');
}
```
The `else` clause is used to provide instructions for what to do if the initial assertion is not `true`. For very complex conditionals, it's possible to provide multiple assertions that can be checked:

```js
let foo = 12;
let bar = 12;

if (foo > bar ) {
    // If `foo` is greater than `bar`, then this code executes.
    console.log('Foo is bigger.');
} else if (foo == bar) {
    // If `foo` and `bar` are equal, then this code executes.
    console.log('Foo and Bar are equal.');
} else {
    // If `bar` is greater than `foo`, this code will execute.
    console.log('Bar is bigger.');
}
```
In the example above, the `else if` clause provides a second assertion that is checked. If the first assertion is `true`, then the second assertion will never be checked. But if the first assertion is `false`, then the second assertion will be checked. If the second assertion is `true`, then that code executes. If the second assertion is also `false`, then the `else` clause will be executed.

Of course, it is possible to nest conditionals to create even more complex conditionals:
```js
let foo = 12;
let bar = 42;
let baz = 7;

if (foo > bar ) {
    console.log('Foo is bigger than bar.');
    if (foo > baz) {
        console.log('Foo is bigger than baz, so it is the biggest!);
    } else {
        console.log('Baz is bigger than foo, so it is the biggest!);
    }
} else if (foo == bar) {
    // If `foo` and `bar` are equal, then this code executes.
    console.log('Foo and Bar are equal.');
    if (foo == baz) {
        console.log('Foo, bar, and baz are all equal.');
    } else if (foo > baz) {
        console.log('Foo and bar are larger than baz.');
    } else {
        console.log('Foo and bar are smaller than baz.');
    }
} else {
    // If `bar` is greater than `foo`, this code will execute.
    console.log('Bar is bigger than foo.');
    if (bar > baz) {
        console.log('Bar is bigger than baz, so it is the biggest!);
    } else {
        console.log('Baz is bigger than bar, so it is the biggest!);
    }
}
```
As you can see in the example above, we can nest conditionals in all kinds of ways to achieve whatever logical control we need. 

## Comparison Operators
In order to make assertions that conditional statements can check, we must use a few more operators. We are often making comparisons between values, so the [comparison operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Comparison_operators) are important. We can see comparison operators at work in the examples above, but there are more than those. Here is a chart of commonly used comparison operators:

operator | description | example 
---------|-------------|--------
`==` | **Equal**: Returns `true` if the operands on either side of the operator are equal. | `x == y`
`!=` | **Not Equal**: Returns `true` if the operands on either side of the operator are *not* equal. | `x != y`
`===` | **Strict Equal**: Returns `true` if the operands are equal and of the same type. | `x === 2`
`!==` | **Strict Not Equal**: Returns `true` if the operands are of the same type but not equal, or are of different type. | `x !== 'text'`
`>` | **Greater Than**: Returns `true` if the left operand is greater than the right operand. | `x > 42`
`>=`| **Greater Than or Equal To**: Returns `true` if the left operand is greater than or equal to the right operand. | `foo >= 32`
`<` | **Less Than**: Returns `true` if the left operand is less than the right operand. | `y < 1337`
`<=` | **Less Than or Equal To**: Returns `true` if the left operand is less than or equal to the right operand. | `bar <= 42`

Using these comparison operators we can compare the values of any two variables.

## Logical Operators
Sometimes when we want to check especially complex conditionals, it's useful to utilize [logical operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Logical_operators) to make compound assertions. There are three main logical operators:

operator | description | example
---------|-------------|---------
`&&` | **AND**: Returns `true` if BOTH operands equal `true`. | `x == 12 && y == 42`
&#124;&#124; | **OR**: Returns `true` if EITHER operand equals `true`. | `x > 3` &#124;&#124; `y < 31`
`!` | **NOT**: Returns the opposite of whatever the operand evaluates to be. That is `false` if the operand equals `true`, or `true` if the operand equals `false`. | `!foo`

These three logical operators round out our ability to check conditions between operands. `AND` and `OR` are especially useful for making compound assertions. We can use them in a conditional like this:

```js
let x = 12;
let y = 42;

if (x==12 && y==42){
    // This code would execute because both `x==12` and `y==42` are `true`.
    console.log('This is true!');
}

if (x==144 && y==42){
    // This code would not execute because one side of the assertion is `false`.
    // The `AND` operator requires both sides to evaluate to `true`.
    console.log('This is true!');
}

if (x==36 || y==42) {
    // This code would execute because although `x==36` is `false`, the other side of the assertion is true.
    // This happens because of the `OR` operator.
    console.log('One of these is true!');
}
```

Although it can be tricky if we string together several `AND` or `OR` clauses in an assertion, these example keep things simple. It's often best when writing code to keep things simple and break out complex logic into multiple conditionals.

It can sometimes be tougher to understand the `NOT` operator because it equals `true` when the value is `false`. This can be a bit of a head trip. Here is an example using `NOT`:

```js
let loggedIn = false;

if (!loggedIn) {
    // Since `loggedIn` is `false`, this code will execute.
    console.log('This user is not logged in!');
}
```

## Truthiness and Falsiness
Just like with Data Types, JavaScript is more than happy to attempt to arrive at a `true` or `false` value based on whatever we give it. Sometimes this can be very convenient. In JavaScript we have a notion of ["truthy"](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) and ["falsy"](https://developer.mozilla.org/en-US/docs/Glossary/Falsy).

The following values all evaluate to `true` in a conditional:

```js
if (true)
if (12)
if ("some text")
if ({})
if ([])
if (3.14)
```

Likewise, the following values all evaluate to `false` in a conditional:

```js
if (false)
if (null)
if (undefined)
if (0)
if (NaN)
if ('')
if ("")
```

Using the principles of truthy and falsy, we could write a conditional like this:

```
let x;

if(x) {
    // This code would execute if `x` has any value assigned other than `null` or `undefined`.
    // Since `x` is currently equal to `undefined`, this code will NOT execute.
} else {
    // This code will execute.
    console.log('X exists, but it has no value.');
}
```

Of course, when possible it's good to check explicitly against an expected value. If we expect `x` to be `undefined` then we should check for that (`if (x===undefined)`). But sometimes that is not possible. Given the dynamic typing of JavaScript and the complex nature of programs, we might find a situation where we are not sure if a value might be `undefined` or `null`, but we want to catch that condition regardless. Or, we might consider `0`, and `false` to be equivalent for some purpose in our code. In this case, it is helpful to be able to perform truthy and falsy checks. 

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.



{% exercise %}
Write a conditional to check if `x` and `y` are equal. If so, set `status` to "success". If not, set `status` to "failure".

{% initial %}
let x = 12;
let y = 42;
let status;

{% solution %}
let x = 12;
let y = 42;
let status;

if (x==y) {
    status = "success";
} else {
    status = "failure";
}

{% validation %}
assert(status=="failure", "Incorrect. Please be sure to set the status variable accordingly.");

{% endexercise %}

{% exercise %}
Write a conditional to check if `x` OR `y` are true. If so, set `status` to "success".

{% initial %}
let x = true;
let y = false;
let status;

{% solution %}
let x = 12;
let y = 42;
let status;

if (x || y) {
    status = "success";
}

{% validation %}
assert(status, "Incorrect. Please be sure to set the status variable accordingly.");

{% endexercise %}

{% exercise %}
Write a conditional to check if `x` AND `y` are true. If so, set `status` to "success". If not, set `status` to "failure".

{% initial %}
let x = true;
let y = false;
let status;

{% solution %}
let x = 12;
let y = 42;
let status;

if (x && y) {
    status = "success";
} else {
    status = "failure";
}

{% validation %}
assert(status, "Incorrect. Please be sure to set the status variable accordingly.");

{% endexercise %}











