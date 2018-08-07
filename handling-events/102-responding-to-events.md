# Responding to Events

When an event listener detects an event signal in the system, it executes the specified function, which we call an _event handler_. This can be a named function or an anonymous function. The event listener passes in the `Event` object, which contains information about the event itself including the `target` of the event (which is usually the button or link that was clicked, the form that was submitted, etc.). We can use all of these components of an event to make decisions in our code about what lines to execute next. 

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
Each event signal detected in the system triggers a call to the event handler that is defined in the event listener. The function that handles the event always receives an `Event` object as a parameter. This object can be used to access different information about the event. Here is an example of using information from the `Event` object within an event handler.

```js
let button = document.querySelector('button');
button.addEventListener('click', function(event){
    console.log(`Action was triggered by ${event.target} at ${event.timestamp}.`);
    event.target.style.backgroundColor = 'goldenrod';
    let itemID = event.target.dataset.itemID;
});
```

There are several attributes, like `Event.timestamp` that can be used to respond to events signals, but the most common aspect of the `Event` object to use within an event handler is the `Event.target` object. `Event.target` is the DOM element object that triggered the event handler. In the example above, `event.target` is the `button` object.

Within the event handler, `event.target` can be used to access any information stored in the DOM element object. We can alter attributes of the object (such as the style alteration in the example code), and we can read in any attribute values (such as the `itemID`, which is read from the `event.target.dataset` object). This means we can use the same event to handle multiple elements on the page. Consider the following example of a system where favoriting content is possible.

**html**
```html
<ul id="search-results">
    <li>Content Item Title 1 <a class="fave-link" href="#favorite" data-contentId="1">Add to favorites</a></li>
    <li>Content Item Title 2 <a class="fave-link" href="#favorite" data-contentId="2">Add to favorites</a></li>
    <li>Content Item Title 3 <a class="fave-link" href="#favorite" data-contentId="3">Add to favorites</a></li>
    <li>Content Item Title 4 <a class="fave-link" href="#favorite" data-contentId="4">Add to favorites</a></li>
    <li>Content Item Title 5 <a class="fave-link" href="#favorite" data-contentId="5">Add to favorites</a></li>
</ul>
```

**js**
```js
let faveLinks = document.querySelectorAll('.fave-link');
for (let link of faveLinks) {
    link.addEventListener('click', function(event){
        console.log(`Adding ${event.target.dataset.contentId} to user favorites.`);
    });
}
```
In the example above, we have some HTML that contains multiple content item listings. Each item has a "fave link" that allows a user to add the item to their "Favorites" list. Each of those links has a `data-contentId` attribute that stores the ID for the content item.

In our JavaScript, we have used a `document.querySelectorAll()` command to select all of the links, and then we loop through each link and add an event listener that will call an anonymous function. The anonymous function can then access the `event.target.dataset.contentId` property to determine which content item should be saved to the user's favorites list in the database. This allows us to use the same event listener to respond to event triggers in slightly different ways. Obviously we could not write a separate event listener for each content item in our database, so it's crucial to be able to pass in data using this method. The `Event.target` object allows us to make full use of the HTML `data-` attributes to pass data around in our web application.

## Preventing Default Actions
Sometimes when we are responding to event triggers, we need to prevent the default action of the browser. This happens a lot when we are building more complex JavaScript applications that use elements like forms and links to provide user interface components. But it also comes up when we are using JavaScript to provide client-side validation of form inputs or allow for users to do smaller changes to the interface. If we write enough JavaScript that uses event handling, we are eventually going to need to prevent some default behavior.

Preventing default behavior is as simple as including a single command in our event handler function: [`Event.preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault). This command stops the browser from executing whatever the default action is for that event. Here is an example of using it to provide a form validation.

**html**
```html
<form id="registration-form" action="register/" method="post">
    <p class="errors hidden">No errors to report.</p>
    <label>Username: <input type="text" value="" name="username" required></label>
    <label>Password: <input type="password" value="" name="pass1" required></label>
    <label>Confirm Password: <input type="password" value="" name="pass2" required></label>
    <input type="submit" value="Register">
</form>
```

**js**
```js
let myForm = document.querySelector('#registration-form');
let pass1 = document.querySelector('input[name="pass1"]');
let pass2 = document.querySelector('input[name="pass2"]');
let errorsParagraph = document.querySelector('p.errors');

myForm.addEventListener('submit', function(event){
    if (pass1.value != pass2.value){
        event.preventDefault();
        errorsParagraph.innerHTML = "Password values do not match.";
        errorsParagraph.setAttribute('class', 'errors visible');
    }
});
```

The example above shows the `event.preventDefault()` command used to stop a `form` from submitting when the password fields do not match. This kind of client-side form validation is helpful to a user because it provides an instantaneous feedback about whether or not they filled out the form properly. (**Note:** These sorts of validations are not a substitute for strong validation on the server or database side, too, but they provide a more enjoyable user experience.)

Our custom event handler will execute before the default actions take place in the browser, so we have a chance to determine whether or not we wish for those default actions to happen at all. If not, the `Event.preventDefault()` command stops those actions from happening. This allows JavaScript developers the ability to truly alter the way the browser behaves in order to best serve their users.


## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Add a <code>submit</code> event listener to the <code>form</code> element using an anonymous function.

{% initial %}
let myTest = false;
let form = document.querySelector('form');
// add event listener that executes `myAction()`

{% solution %}
// solution code
let myTest = false;

let form = document.querySelector('form');
form.addEventListener('submit', function(event){
    myTest = true;
});

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

{% exercise %}
Use the <code>event.target</code> object to change the <code>background-color</code> of the element by adding a <code>click</code> event to the <code>button</code> element.

{% initial %}
let button = document.querySelector('button');
// add event listener that changes background-color of button

{% solution %}
//solution code
let button = document.querySelector('button');

button.addEventListener('click', function(event){
    event.target.styles.backgroundColor = 'coral';
});

{% validation %}
assert((triggerCheck===true && event.target.styles.backgroundColor=='coral'), 'Incorrect.');

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
        if (type == "form") {
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
        func(event);
    }
}
var triggerCheck = false;
var document = new MockDoc();

var event = {
    target: {
        styles: {
            backgroundColor: 'gainsboro'
        }
    }
};


{% endexercise %}

{% exercise %}
Use a <code>preventDefault()</code> command to stop the <code>form</code> from submitting unless the user submits both <code>firstName</code> and <code>lastName</code> fields.

{% initial %}
let myForm = document.querySelector('#registration-form');
let firstName = document.querySelector('input[name="first-name"]');
let lastName = document.querySelector('input[name="last-name"]');

// Add submit event listener to `myForm`.
// Verify that both `firstName` and `lastName` have been filled in.

{% solution %}
// solution code
let myForm = document.querySelector('#registration-form');
let firstName = document.querySelector('input[name="first-name"]');
let lastName = document.querySelector('input[name="last-name"]');

myForm.addEventListener('submit', function(event){
    if (!firstName.value || !lastName.value){
        event.preventDefault();
        console.log('Both names are required.')
    }
});


{% validation %}
assert((triggerCheck===true && pdCheck===true), "Incorrect.");

{% context %}

class MockDoc {
    querySelector(q){
        if (q == "form"){
            return new MockElem("form");
        } else {
            return new MockElem("input");
        }
    }
}
class MockElem {
    constructor(type){
        this.children = [];
        this.innerHTML = '';
        this.style = {};
        this.tagName = type;
        this.value = false;
    }
    addEventListener(trigger, func){
        if (trigger === 'submit') {
            triggerCheck = true;
        }        
        func(event);
    }
}
var triggerCheck = false;
var document = new MockDoc();

var pdCheck = false;
event = {};
event.preventDefault = function(){
    pdCheck = true;
};

{% endexercise %}


