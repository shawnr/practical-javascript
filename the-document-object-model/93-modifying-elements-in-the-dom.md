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

We can imagine that on a page with an "add favorite" button there is some JavaScript that will change the text of the button using the `innerHTML` property. This is a simple but common case: changing the text of a button or link to let the user know that an action has been performed. Sometimes it's necessary to change related elements, such as the counter displayed on another HTML element. Using `innerHTML` is a straightforward way to change the textual content of an element.

## Modifying Element Attributes
Sometimes we need to change more than the textual content of an element. We might need to change the `src` attribute of an `<img>` tag, or the `value` attribute of a form input. We may want to change the `width` or `height` of an element, or any number of other HTML attributes. In these cases, it's necessary to be able to "get" and "set" the values of element attributes. To do this, each element provides us with two methods: [`getAttribute`](https://developer.mozilla.org/en-US/docs/DOM/element.getAttribute) and [`setAttribute`](https://developer.mozilla.org/en-US/docs/DOM/element.setAttribute).

Consider this example:

**html**
```
<img src="placeholder.jpg">
```

**js**
```
let image = document.querySelector('.bio img');

if (image.getAttribute('src') == 'placeholder.jpg'){
    image.setAttribute('src', 'new.jpg');
}
```
In this example we can see that the JavaScript code selects the image and then uses `getAttribute()` to retrieve the `src` attribute value. The `getAttribute()` method takes just one parameter: the name of the attribute. It checks that value and, if the values match, it replaces the `src` attribute value with a new filename using `setAttribute()`.

The `setAttribute()` method takes two parameters: the name of the attribute, and the new value.

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