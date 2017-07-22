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

These kinds of custom events can help us build an event-driven system based upon loose coupling. But there are many events pre-defined in JavaScript that we can extend and use to fit our needs.

## Using Built-in Events
There are [many events defined in JavaScript](https://developer.mozilla.org/en-US/docs/Web/API/Event) that can be used to create custom event handlers. Here are a few:

* [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent)
* [`DragEvent`](https://developer.mozilla.org/en-US/docs/Web/API/DragEvent)
* [`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)
* [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
* [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)
* [`GamePadEvent`](https://developer.mozilla.org/en-US/docs/Web/API/GamepadEvent)
* [`ErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent)
* [`PointerEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent)
* [`StorageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/StorageEvent)
* and many more...

If we want to make an event listener that leverages more than the standard "click" style behavior, we can use these events to our advantage. We can intercept `MouseEvent` events and determine the `x, y` coordinates of the mouse pointer. We can listen for `KeyboardEvent` events to provide keyboard shortcuts for our users. Each of these `Event` types offers extra information and extra event signals that we can use in defining our own listeners. For example, the `KeyboardEvent` object makes a `keydown` event signal available. This signal is dispatched whenever the user presses a key on the keyboard.  Here is an example of using `keydown` events to provide some interaction for the user.

```js
document.addEventListener('keydown', function(event){
    console.log(`You pressed the ${event.key} key.`);
}
```
The code above will print a message into the console every time the user presses a key. One of the extra data points the `KeyboardEvent` event gives us is the `event.key` property, which tells us the key that was pressed. Other `KeyboardEvent` events that are dispatched include `keyup`, `keydown`, and `keypressed`. There are also many more properties that can help us build great keyboard interfaces. 

For any family of events we wish to explore, we should read through the documentation so we understand exactly what events they signal and how those events are determined. It's useful to know, for example, the difference between a `keydown` and a `keyup` and the fact that most people want actions to happen on `keyup`, but not on `keydown` (because that's how most systems already work). There is no way to apply a general approach to all of these intricate details, so we must dive into each case on its own.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Add a <code>keyup</code> event listener to the <code>document</code> sets <code>keyCheck</code> to <code>true</code> when the <code>w</code>, <code>a</code>, <code>s</code>, <code>d</code> keys are pressed.

{% initial %}
let keyCheck = false;

// create event listener

// determine which key was pressed

// if `w`, `a`, `s`, `d` keys are pressed, set `keyCheck = true`

{% solution %}
// solution code
let keyCheck = false;

document.addEventListener('keyup', function(event){
    if ( (event.key === 'w') ||
         (event.key === 'a') ||
         (event.key === 's') ||
         (event.key === 'd') ) {
             keyCheck = true;
     }
});

{% validation %}
assert((keyCheck===true && triggerCheck===true), "Incorrect.");

{% context %}
class MockElem {
    constructor(type){
        this.children = [];
        this.innerHTML = '';
        this.style = {};
        this.tagName = type;
    }
    addEventListener(trigger, func){
        if (trigger === 'keyup') {
            triggerCheck = true;
        }        
        func(event);
    }
}
var triggerCheck = false;
var document = new MockElem('document');

var event = { key: 'w' };

{% endexercise %}

