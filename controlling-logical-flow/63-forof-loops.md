# Looping Arrays

The most common use for a loop in JavaScript is to loop over values in an Array. Arrays are meant for storing lists of items, and we often have a need to display those list items in different ways. Arrays are a great way to store and access this information, especially in modern JavaScript.

As we read in the `for` loop section, we can loop through Arrays in a very "manual" way by using a standard `for` loop. However, Arrays (and other iterable objects in JavaScript) can also be accessed using [the `for ... of` syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...of_statement).

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


