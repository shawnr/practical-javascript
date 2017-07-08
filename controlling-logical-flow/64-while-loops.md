# While Loops

The other common kind of loop in programming languages is [the `while` loop](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code#while_and_do_..._while). These loops are defined with an opening assertion, and they execute as long as the condition remains true. Here is an example:

```js
let i = 0;
while (i < 12) {
    console.log(`This is loop iteration number ${i}`);
    i++;
}
```
In this case, the `while` loop will execute 12 times, and it will output a message to the web browser's JavaScript console on each loop. 

The `while` loop provides a way to keep executing some set of instructions until a condition changes. This can be powerful, but it can also be dangerous. It's very easy to write an infinite while loop:

```js
while (true) {
    console.log('This is an infinite loop and will lock up your browser tab if you try to run it. (Don\'t do that!)');
}
```
It might seem insane to have such an easy way to write an infinite loop that could lock up a browser tab, but if used properly, it could work. Imagine we have a system that has a `checkValue()` function that would give us back a value we are watching for:

```js
while (true) {
    status = checkValue();
    if (status.success == true) {
        break;
    }   
}
```
In this example, we set up an infinite loop, but once a status is received and checked, it can stop execution using the `break` command. The `break` command can be used to stop any loop from executing and return to the execution of code outside the loop. (Please note: This is still probably not the best structure for a program, but it works by way of example.)

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.

{% exercise %}
Define a `while` loop that will add 1 to a number until it equals 42.

{% initial %}
let x = 0;

{% solution %}
let x = 0;
while (x < 43) {
    console.log(`The value of x is: ${x}`);
    x++;
}
{% validation %}
assert(x===43, "Incorrect.");

{% endexercise %}


