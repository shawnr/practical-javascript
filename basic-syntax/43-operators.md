# Operators
[Arithmetic Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators) are used to modify numbers in JavaScript. Operators include addition, subtraction, multiplication, and division. These are used throughout code to calculate different values and modify data flowing through the system. 

## Standard Operators
The standard operators are addition, subtraction, multiplication, and division. These operators always take in two numeric values (operands) as their input and return a single numeric value. They operate as we expect:

```js
let a = 2 + 2; // Sets the variable "a" equal to 4.
let b = 2 - 2; // Sets the variable "b" equal to 0.
let c = 2 * 2; // Sets the variable "c" equal to 4.
let d = 2 / 2; // Sets the variable "d" equal to 1.
```
We could also use operators to calculate the value between variables:

```js
let e = c * a; // Sets the variable "e" equal to 16.
```

## Advanced Operators
In addition to the standard operators, there are advanced operators that we often use to do calculations in JavaScript. These operators also accept two numeric values (operands) and return a single numeric value as a result, but their behavior is a little more complex and less obvious than the previous operators.

### Remainder
The `%` operator returns the remainder after the two operands are divided. Here are some examples:

```js
let a = 4 % 2; // Sets the variable "a" equal to 0;
let b = 5 % 2; // Sets the variable "b" equal to 1;
```
In the example above, we can see that `a` is equal to `0` because `4 / 2 = 2` and there is no remainder. But `b` is equal to `1` because `5 / 2` equals `2` with a remainder of `1`. 

This may seem like an odd way to express division. After all, most of the time we are happy to know that `5 / 2 = 2.5`. But knowing whether there is a remainder after division, and what the value of that remainder is, can be useful. For example, in order to determine if we're dealing with an even or odd number, we can check the remainder of any number after dividing by `2`:

```js
let c = 1236 % 2; // Sets the variable "c" equal to 0;
```

If we were, for example, trying to color rows of a table differently to increase readability, we could check for "even/odd" and then add a class accordingly. If `c = 0` then we would know that row is "even".

### Exponent

Sometimes we need to find the value of some number raised to some exponent. This is used to calculate all sorts of equations in Geometry, Physics, or numerous other situations. In order to do that we use the `**` notation:

```js
let a = 2**4; // Sets the value of "a" to 16.
```
In this example, we are not multiplying `2 * 4` (which would be `8`). We are raising the number `2` to the exponent `4` (we usually describe this as "two to the fourth power"). This is equivalent to `2 * 2 * 2 * 2`, which equals `16`.

### Increment

We often use different variables to count things in our programs. This happens all the time: counting times through a loop, items in a list, votes, etc. Because it's such a common thing to do, there is a shorthand for how we write it. We could write:

```js
let counter = 0; // Initialize "counter" to 0.
counter = counter + 1; // Sets the value of "counter" to 1.
```

The code above works, but it can be shorthanded like this:

```js
let counter = 0; // Initialize "counter" to 0.
counter++; // Sets the value of "counter" to 1.
```

Whenever `counter++` is executed in the code, it will increase the value of `counter` by `1`.

### Decrement
As a companion operator to the increment operator, decrement uses the `--` symbol to denote that a value should be decremented by `1`. Here is an example:

```js
let counter = 100; // Initialize "counter" to 100.
counter--; // Sets the value of "counter" to 99.
```

Each time `counter--` is run it would decrease the value of `counter` by `1`. 

## Grouping Operations

Just like with normal arithmetic, we can group operations using parentheses. The normal [order of operations](https://en.wikipedia.org/wiki/Order_of_operations) is maintained in JavaScript, and parentheses affect computation just as they would in regular math. For example:

```js
let x = 12;
let y = 3.14;

let z = x + y * 3 - (x - y/2);
```
The value of `z` would be `10.990000000000002`. Following the order of operations, JavaScript would first figure out `y/2` (which is `1.57`). Then it would calculate `x - 1.57` to get `10.43`. Next it would figure out `y * 3`, which is `9.42`. Finally, it would work out `x + 9.42 - 10.43`. For some reason, thanks to the inaccuracy of Decimal data types in JS (again, we will cover this more later), the final result is `10.990000000000002`. Normally we would run another command to round that down to `10.99`.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Set `x` equal to three times seven.

{% initial %}
let x =

{% solution %}
let x = 3 * 7;

{% validation %}
assert(x == 21);

{% endexercise %}

{% exercise %}
Set `x` equal to twelve minus eight.

{% initial %}
let x =

{% solution %}
let x = 12 - 8;

{% validation %}
assert(x == 4);

{% endexercise %}

{% exercise %}
Set `x` equal to seven to the twelfth power.

{% initial %}
let x =

{% solution %}
let x = 7**12;

{% validation %}
assert(x == 7**12);

{% endexercise %}

{% exercise %}
Add parentheses so the value of `x` equals `42`.

{% initial %}
let x = 6 + 2 * 3 * 4 - 2 * 3;

{% solution %}
let x = (6 + 2 * 3) * 4 - (2 * 3);

{% validation %}
assert(x == 42);

{% endexercise %}