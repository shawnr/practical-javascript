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
var foo = 12;
var bar = 42;

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
var foo = 12;
var bar = 12;

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
var foo = 12;
var bar = 42;
var baz = 7;

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

## Logical Operators

{% exercise %}
Define an Object called `foo` with a `name` attribute equal to "Bob".

{% initial %}
var 

{% solution %}
var foo = {};
foo.name = "Bob";

{% validation %}
assert(foo.name==="Bob", "Incorrect.");

{% endexercise %}


