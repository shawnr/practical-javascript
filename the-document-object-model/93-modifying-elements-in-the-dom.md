# Modifying Elements
In addition to adding and removing elements from the DOM, it's important to be able to alter elements to reflect changes, updates, and other system status. These changes are not just changes in the text or information presented to the user, but also to the attributes and status of the elements in the DOM. It's necessary to consider all of the ways in which DOM elements may be modified by running JavaScript.

## Modifying the Content of Elements
The content of elements is generally accessed through the `innerHTML` property. This property can be used to either retrieve the contents of an element (and all of its child elements) or to set those contents to something new. It's often useful to use `innerHTMl` when setting the text value of an element that contains no child elements. Consider the following example:

**html**
```html
<button id="123" class="favorite not-favorited">Click to add Favorite!</button>
```

**js**
```js
let button = document.querySelector('#123');
button.innerHTML = "Added to Favorites!";
```

We can imagine that on a page with an "add favorite" button there is some JavaScript that will change the text of the button using the `innerHTML` property. This is a simple but common case: changing the text of a button or link to let the user know that an action has been performed. Sometimes it's necessary to change related elements, such as the counter displayed on another HTML element. Using `innerHTML` is a straightforward way to change the content of an element.

## Modifying Element Attributes

## Modifying Element Styles


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