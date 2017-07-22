# Responding to Events

When an event listener detects an event signal in the system, it executes the specified function. This can be a named function or an anonymous function. The event listener passes in the `Event` object, which contains information about the event itself including the `target` of the event (which is usually the button or link that was clicked, the form that was submitted, etc.). We can use all of these components of an event to make decisions in our code about what lines to execute next. 

Let's take a look at more examples of how we can use this information to respond to events, and how to prevent default browser actions from executing when an event is triggered.

## Named vs. Anonymous Functions
There are two ways to define the functions that are executed when an event signal is detected by an event listener. The way used in the examples in the previous section uses a _named function_ that is executed when the listener detects an event signal. Here is an example.

```js
function myAction(event){
    console.log('My action has been triggered!');
}

let button = document.querySelector('button');
button.addEventListener('click', myAction);
```
In the example above, we define a function called `myAction()` that accepts a parameter called `event`. Then we select a `button` element from the DOM and add an event listener watching for the `'click'` event. This approach is clear and easy to read, and it allows for the same action to be attached to multiple events. In the case where you need to add a listener that would call the `myAction()` function to multiple DOM elements, this could be a more efficient and clear way to do so.

However, we often want to add a singular event listener to a single DOM element. In this case, many developers consider it more efficient and just as clear to create an event listener that calls an _anonymous function_. Here is an example of that approach.

```js
let button = document.querySelector('button');
button.addEventListener('click', function(event){
    console.log('My action has been triggered!');
});
```
The result of this code is exactly the same as the code in the previous example: An event listener is added to a `button` element in the DOM that causes a function to be executed that, in this case, writes a log message to the console. We can understand why some developers prefer this approach because it uses fewer lines of code and it keeps all of the logic directly connected to the event listener contained within that code block. JavaScript makes a lot of use of anonymous functions in many situations, so this is not an unusual style choice.

## Using Event Objects

## `stopPropagation()`

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Define a problem.

{% initial %}
// initial code 

{% solution %}
// solution code

{% validation %}
assert(true), "Incorrect.");

{% endexercise %}