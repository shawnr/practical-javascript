# HTML Data Attributes
A feature of HTML that is often overlooked by non-developers is the ability to create ["data" attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*) on HTML elements that can store specific data values. These properties can be named (almost) whatever we want as long as they are preceded by the `data-` prefix. We could create properties such as `data-id`, `data-title`, `data-username`, etc. We can put as many of these attributes onto an HTML element as we would like. 

Using HTML data attributes, we can retrieve a lot of information that is useful for making different features on our websites. Returning to our old example of a "Add to Favorites" button, it would not be uncommon to use a data attribute to carry through the ID of the content item being favorited. Here's an example:

**html**
```html
<button data-contentID='1234' data-title='Fascinating Article'>Add to Favorites!</button>
```

**js**
```js
let faveButton = document.querySelector('button');
console.log(faveButton.dataset.contentID); // prints "1234" to the console
console.log(faveButton.dataset.title); // prints "Fascinating Article" to the console
```

In this example, we've used data attributes to store the `contentID` and the `title`. We can select this button however we wish in JavaScript, and then we can access the values of these attributes by accessing the `faveButton.dataset` object. We can also change values, or add values, to the `faveButton.dataset` object to facilitate whatever logic we need.

Every DOM element we select in JavaScript has an `element.dataset` object attached to it. We can make full use of this object to manage our data needs and make sure that our code can access that information when we need to. At this point, we have only been manually selecting elements in the DOM, but in the next section we will put everything together to respond to user interactions with the DOM using "event handlers". These HTML data attributes are even more handy when we are actually working with events initiated by our users.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Define a problem.

{% initial %}
// initial code 

{% solution %}
// solution code

{% validation %}
assert(true, "Incorrect.");

{% endexercise %}