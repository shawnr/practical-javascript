# Custom Events
Although we are often working with existing events that are triggered by elements in the DOM according to their specifications (things like "click", "submit", "mouseover", etc.), sometimes we want to create our own events based on actions in the system. We might have various processes happening in an asynchronous fashion, or we might want to alert people of new items available on a feed, or we could kick off a loosely coupled custom process based on our specific requirements. There are many reasons for creating a custom event, and they are not too difficult to manage.

## General Purpose Custom Events
In order to create a custom event, we must first create a new `Event` object, and then we must create some listener to watch for our new event. When we wish to trigger the event we use the `document.dispatchEvent()` method, which also exists on all DOM elements. 

```js
let publishCompleted = new Event('publishCompleted');

let notification = document.querySelector('#notification');

notification.addEventListener('publishCompleted', function(event){
    event.target.innerHTML = "Publishing has completed.";
});

document.dispatchEvent(publishCompleted);
```

In the example above, we see that a new `Event` object is created for a `'publishCompleted'` event. This `Event` can now be dispatched whenever we need. The `notification` object is a DOM element that has an event listener watching for the `'publishCompleted'` signal. When it detects the `'publishCompleted'` event signal, it will trigger an anonymous function that changes the text of the `notification` element (since `notification` is the `event.target` in this case).


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

