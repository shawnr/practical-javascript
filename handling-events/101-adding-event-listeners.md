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
    if(event.target.style.backgroundColor === "cornflowerblue"){
        event.target.style.backgroundColor = "pink";
    } else {
        event.target.style.backgroundColor = "cornflowerblue";
    }
}

button.addEventListener('click', changeColor);
```

The result of the code above is this button:

<button id="color-changer">Click me to change color.</button>
<script>
let button = document.querySelector('#color-changer');

function changeColor(event){
    if(event.target.style.backgroundColor === "cornflowerblue"){
        event.target.style.backgroundColor = "pink";
    } else {
        event.target.style.backgroundColor = "cornflowerblue";
    }
}

button.addEventListener('click', changeColor);

</script>


In this example we use the same method to apply the event listener to the button as we did to apply the event listener to the form. We must first select the element to which we want to attach a listener. Then, we define the function that will be executed when the listener is triggered (when it detects the event signal). Finally, we attach the listener to the DOM element using the `addEventListener()` method. 

This process is repeated often throughout a complex web app. Event listeners are, literally, the things that make our interfaces move. When properly applied, they can give us a compelling user experience impossible without the logic of JavaScript.

There are many more intricacies to successfully handling events, but we will get to those on the next pages.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Add a <code>click</code> event listener to the <code>button</code> element.

{% initial %}
let myTest = false;
function myAction(event){
    myTest = true;
}
let button = document.querySelector('button');
// add event listener that executes `myAction()`

{% solution %}
// solution code
let myTest = false;
function myAction(event){
    myTest = true;
}
let button = document.querySelector('button');
button.addEventListener('click', myAction);

{% validation %}
assert((myTest===true && triggerCheck===true), "Incorrect.");

{% context %}
class MockDoc {
    querySelector(q){
        if (q == "button"){
            return new MockElem("button");
        } else {
            return null;
        }
    }
    createElement(type){
        if (type == "button") {
            return new MockElem("BUTTON");
        } else {
            return null;
        }
    }
}
class MockElem {
    constructor(type){
        this.children = [];
        this.innerHTML = '';
        this.style = {};
        this.tagName = type;
    }
    addEventListener(trigger, func){
        if (trigger === 'click') {
            triggerCheck = true;
        }        
        func();
    }
}
var triggerCheck = false;
var document = new MockDoc();



{% endexercise %}

{% exercise %}
Add a <code>submit</code> event listener to the <code>form</code> element.

{% initial %}
let myTest = false;
function myAction(event){
    myTest = true;
}
let form = document.querySelector('form');
// add event listener that executes `myAction()`

{% solution %}
// solution code
let myTest = false;
function myAction(event){
    myTest = true;
}
let form = document.querySelector('form');
form.addEventListener('submit', myAction);

{% validation %}
assert((myTest===true && triggerCheck===true), "Incorrect.");

{% context %}

class MockDoc {
    querySelector(q){
        if (q == "form"){
            return new MockElem("form");
        } else {
            return null;
        }
    }
    createElement(type){
        if (type == "form") {
            return new MockElem("FORM");
        } else {
            return null;
        }
    }
}
class MockElem {
    constructor(type){
        this.children = [];
        this.innerHTML = '';
        this.style = {};
        this.tagName = type;
    }
    addEventListener(trigger, func){
        if (trigger === 'submit') {
            triggerCheck = true;
        }        
        func();
    }
}
var triggerCheck = false;
var document = new MockDoc();



{% endexercise %}