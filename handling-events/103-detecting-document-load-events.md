# Detecting Document Load Events

Early in this book we discussed the ways in which we [attach JavaScript to a web page](/basic-syntax/41-adding-javascript-to-an-html-file.md). We discussed the fact that we prefer to use external JavaScript files that are linked with `<script>` tags, and we mentioned that we should use either the `async` or `defer` attributes to prevent our JavaScript from "blocking" the load of other page assets. 

Since the web is a dynamic place, and different resources for a page could be coming from all over the world, we can never know for sure how long it will take for a user to receive all of the page resources or how long it will take to parse everything on the user's unique hardware. There is no certainty of order of download for most page resources, and it's completely possible for unexpected thing to happen during the load process. It is possible, and sometimes likely, that your JavaScript file will finish downloading and begin processing before the HTML of your page has completed downloading.

As we've been manipulating the DOM and adding listeners to DOM elements, it may have occurred to us that in some situations we could receive errors if our JavaScript were running before the HTML of the page had actually finished downloading. In general, it is not safe to perform operations on the HTML of our web pages before the file has been completely downloaded and parsed into the DOM.

Luckily, there is a way of knowing when the DOM has finished loading the HTML content of the page.

## The `DOMContentLoaded` Event

As we mentioned in the previous section, there are many events that are triggered by default in the process of viewing a web page. These events are being handled by default actions, but they are ignored by our code until we create a specific event listener. In order to prevent the problem of executing JavaScript that is trying to manipulate a partially-loaded DOM (because the HTML file has not completed downloading), we can set up an event listener for the [`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/Events/DOMContentLoaded) event.

The `DOMContentLoaded` event can be used just like any other event trigger (click, submit, etc.). We often attach an event listener to the `document` object that will execute our code when the `DOMContentLoaded` signal is sent. Let's imagine what that would look like in the context of an HTML-based game:

```js
document.addEventListener('DOMContentLoaded', function(event){
    // Execute any functions that will manipulate the DOM
    setUpGameBoard();
    setUpScoreBoard();
    runGame();
});
```
We can imagine that this event listener is defined as the first block of code in the main JavaScript file for this web-based game. It is waiting for the `DOMContentLoaded` signal, and when that event is triggered it will execute a set of functions that appear to set up the game environment and kick off the execution of the game code. We can imagine that the `setUpGameBoard()` and `setUpScoreBoard()` functions do some significant DOM manipulation to create those structures. We can also assume that running the game will continue to alter those DOM elements as the game progresses. 

Because so much DOM manipulation is happening, it's crucial for the full DOM to be loaded and available within the JavaScript context. If our code were trying to manipulate a partially-loaded DOM element, then we may run into errors due to some element not yet being loaded. By using an event listener with the `DOMContentLoaded` trigger we make sure that we never try to operate on a partially-loaded DOM.

<div class="tip-box">
<h2>Avoid the Load</h2>

<p>The <code>load</code> and <code>DOMContentLoaded</code> events are often confused and used in appropriately. Most of the time, when we are concerned about whether a DOM element will have been loaded in order to be modified or selected, we want to use <code>DOMContentLoaded</code>. However, developers sometimes mistakenly use <code>load</code> instead.</p>

<p>Waiting until the <code>load</code> event is triggered could significantly impact your user because that event signal is not dispatched until after all of the resources for the page have loaded. This includes the images, audio, and video files that might be used in specific ways on the page. There could be a dramatic difference between time it takes to dispatch the <code>DOMContentLoaded</code> event signal and the <code>load</code> signal.</p>

</div>

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Create an event listener that will watch for the  <code>DOMContentLoaded</code> signal before it executes the <code>changeDOM()</code> function.

{% initial %}
// create event listener on `document` object

// execute `changeDOM()` within event listener

{% solution %}
// solution code
document.addEventListener('DOMContentLoaded', function(event){
    changeDOM(event);
});


{% validation %}
assert((triggerCheck===true && changeCheck===true), "Incorrect.");

{% context %}
class MockElem {
    constructor(type){
        this.children = [];
        this.innerHTML = '';
        this.style = {};
        this.tagName = type;
        this.value = false;
    }
    addEventListener(trigger, func){
        if (trigger === 'DOMContentLoaded') {
            triggerCheck = true;
        }        
        func(event);
    }
}
var triggerCheck = false;
var document = new MockElem();

event = {result: true};

var changeCheck = false;
function changeDOM(event){
    changeCheck = event.result;
}

{% endexercise %}


