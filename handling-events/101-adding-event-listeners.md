# Adding Event Listeners
In order to use events in our code, it's important for us to create "event listeners". These are functions that watch for a particular event to be emitted in the JavaScript system and then execute when they detect that signal. It can be a little tricky to grasp exactly how events get triggered at first, but once we can understand and create listeners we can do amazing things with our events.

## Creating Listeners
To create an event listener, we must first select a DOM element. Different DOM elements emit different events. For example, a `form` element will emit the `reset` and `submit` events. Once we select the DOM element, we can use the [`Element.addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) method to create a new listener in our program. That means that if we wanted to respond to a form submission we could use the following HTML and JS code.

**html**
```html
<form id="message-form" action="/some/action/" method="POST">
    <input type="text" name="message">
    <input type="submit" name="Send Message">
</form>
```

**js**
```js
let messageForm = document.querySelector('#message-form');

function handleFormSubmission(event){
    // Code that does something when the form is submitted.
    console.log(`Form has been submitted.`);
}
messageForm.addEventListener('submit', handleFormSubmission);
```

In this example, we have selected the form with the ID `#message-form`. This is stored in the `messageForm` variable. We then use the `addEventListener()` method, which exists on every DOM element, to create a `submit` event listener. This means that anytime the user clicks the "Send Message" button to submit this form, the `submit` event will be emitted. That signal will be picked up by this listener, and the function named in the second parameter of the method call will be executed.

Here is another example that creates a `button` that changes color.

**html**
```html
<button id="color-changer">Click me to change color.</button>
```

**js**
```js
let button = document.querySelector('#color-changer');

function changeColor(event){
    if(event.target.style.backgroundColor === "blue"){
        event.target.style.backgroundColor = "red";
    } else {
        event.target.style.backgroundColor = "blue";
    }
}

button.addEventListener('click', changeColor);
```

<button id="color-changer">Click me to change color.</button>
<script>
let button = document.querySelector('#color-changer');

function changeColor(event){
    if(event.target.style.backgroundColor === "blue"){
        event.target.style.backgroundColor = "red";
    } else {
        event.target.style.backgroundColor = "blue";
    }
}

button.addEventListener('click', changeColor);

</script>


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