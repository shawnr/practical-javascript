# Adding Event Listeners
In order to use events in our code, it's important for us to create "event listeners". These are functions that watch for a particular event to be emitted in the JavaScript system and then execute when they detect that signal. It can be a little tricky to grasp exactly how events get triggered at first, but once we can understand and create listeners we can do amazing things with our events.

## Creating Listeners
To create an event listener, we must first select a DOM element. Different DOM elements emit different events. For example, a `form` element will emit the `reset` and `submit` events. That means that if we wanted to respond to a form submission we could use the following HTML and JS code.

**html**
```html
<form id="message-form" action="/some/action/" method="POST">
    <input type="text" name="message">
    <input type="submit" name="Send Message">
</form>
```

```js
let messageForm = document.querySelector('#message-form');
messageForm.addEventListener('submit', function(event){
    // Code that does something when the form is submitted.
    
}
```

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