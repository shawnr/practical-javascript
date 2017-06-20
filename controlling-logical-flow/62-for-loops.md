# For Loops
The most common kind of loop in any programming language is probably [the `for` loop](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code#The_standard_for_loop). This is a structure that allows us to define a clear number of times to loop through some set of instructions. The `for` loop can be used anytime we need to repeat a set of instructions for a specific number of iterations.

Here is an example of a `for` loop in JavaScript:

```js
for(let i=0; i<10; i++) {
    console.log(`This is iteration number ${i}.`);
}
```
The `for` loop structure is not too complex, but it does require a specific syntax to make it happen. First, it identifies as a `for` loop with the keyword `for`. Then we list three statements in the top line of the loop: 

1. **Initializer:** The first statement initializes a counter variable to a value. (This could be any variable name, but the letter `i` for "iteration" is often used.) This is the value where the counter will begin.
2. **Exit Condition:** The second statement provides a conditional assertion that is checked on each iteration of the loop. Each time the loop executes, it checks this assertion to see if it's `true`. If so, the loop continues. If not, the loop stops.
3. **Final Expression:** third statement increments the value of the counter by one. This causes the value of the counter to increase, so eventually the second statement will return `false`.



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


