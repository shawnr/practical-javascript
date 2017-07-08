# Looping Arrays

The most common use for a loop in JavaScript is to loop over values in an Array. Arrays are meant for storing lists of items, and we often have a need to display those list items in different ways. Arrays are a great way to store and access this information, especially in modern JavaScript.

As we read in the `for` loop section, we can loop through Arrays in a very "manual" way by using a standard `for` loop. However, Arrays (and other iterable objects in JavaScript) can also be accessed using [the `for ... of` syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...of_statement).

Let's look at the example we saw on the `for` loop page:

```js
let simpsons = ['Homer', 'Marge', 'Bart', 'Lisa', 'Maggie'];

for (let i=0; i<simpsons.length; i++){
    console.log(simpsons[i]);
}
```
The above code shows the old way of accessing items in an Array. Here is the new (and preferred) approach:

```js
let simpsons = ['Homer', 'Marge', 'Bart', 'Lisa', 'Maggie'];

for (let familyMember of simpsons){
    console.log(familyMember);
}
```
As we can see, using the `for ... of` syntax allows us to eliminate the need for a counter. Every item in the Array comes through and is accessible within the loop using the named variable we specify at the beginning of the loop (in this case, that variable is named `familyMember`).

The syntax to declare this kind of loop is more simple than the standard `for` loop syntax. We only have to define a name for each item in the Array to take on as it moves through the loop. Everything else is handled for us by JavaScript, which knows how many items are in the Array and can figure out how many times to execute the loop.

This pattern exists in many other programming languages, so getting used to the way this works is helpful even outside of JavaScript. Many templating languages, for example, have a `foreach` or similar kind of loop that can be executed.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Write a `for ... of` loop to add all the numbers in the `transactions` Array.

{% initial %}
let transactions = [23, 44, 7, 89];
let total = 0;

{% solution %}
let transactions = [23, 44, 7, 89];
let total = 0;
for (let amount of transactions) {
    total = total + amount;
}

{% validation %}
assert(total==163, "Check your syntax and math!");

{% endexercise %}


