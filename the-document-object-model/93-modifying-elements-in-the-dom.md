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

The `setAttribute()` method takes two parameters: the name of the attribute, and the new value. You can set as many attributes as you need, but it requires a separate instruction for each one.

Here is another example that demonstrates creating a new DOM element and adding attributes to it.

```js
let myForm = document.querySelector('#myform');

let newInput = document.createElement('input');
newInput.setAttribute('name', 'username');
newInput.setAttribute('value', '');
newInput.setAttribute('placeholder', 'Enter Your Username');
newInput.setAttribute('type', 'text');

myForm.appendChild(newInput);
```
In this example, a new text input is created for a form. The `name`, `value`, `placeholder`, and `type` attributes are set using `setAttribute()`. The input is appended to the `form` element with the ID `#myform`.

It is also possible to remove an attribute altogether with the [`removeAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute) method. Consider this HTML and JavaScript example:

**html**
```html
<input name="username" type="text" value="myusername" disabled="true">
```

**js**
```js
let usernameInput = document.querySelector('input[name="username"]');
usernameInput.removeAttribute('disabled');
```

In this example, the text input called `username` has been disabled. The JavaScript selects that text input and removes the `disabled` attribute, which would allow a user to edit this field. This is a common use case for providing safe access to data. Form fields use a lot of attributes to control behavior, so these methods are especially useful for working with form field DOM elements.

Between `setAttribute()` and `removeAttribute()` we have solid tools for modifying more than the textual content of a DOM element. These are powerful methods that can help in many cases.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section. The exercises in this section all assume the following HTML. Please write JavaScript as if it is attached to this HTML snippet:

```html
<button class="btn save">Save Item</button>
```

{% exercise %}
Given the HTML above, write JavaScript to change the text on the button to read "Saved!" and change the class attribute to be "btn saved".

{% initial %}
// Select the button from the DOM using document.querySelector(). 
let saveButton = 

// Change the innerHTML of the button

// Change the class attribute



{% solution %}
// Set `resultsList` equal to the DOM element for the search-results list. 
let saveButton = document.querySelector('button');

// Change the innerHTML of the button
saveButton.innerHTML = "Saved!";

// Change the class attribute
saveButton.setAttribute('class', 'btn saved');

{% validation %}
assert(saveButton.innerHTML=="Saved!", "Incorrect.");

{% context %}
class MockDoc {
    querySelector(q){
        if ((q == "button") ||
            (q == "button.save") ||
            (q == ".save") ||
            (q == ".btn.save") ||
            (q == "button.btn") ||
            (q == "button.btn.save")){
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
    appendChild(obj){
        this.children.push(obj);
    }
    setAttribute(attr, value){
        this[attr] = value;
    }
}
var document = new MockDoc();

{% endexercise %}