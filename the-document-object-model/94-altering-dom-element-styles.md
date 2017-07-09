# Altering DOM Element Styles
Another task we perform often in our JavaScript programs is altering the visual styling of elements in the DOM. This allows us to create all sorts of interactive visual effects that can provide a compelling experience for the user. Although we can use the `setAttribute()` property on a DOM element to change the classes we have applied, there are other ways to modify styles either in groups or individually.

## The `.style` Attribute

Each DOM element has a `.style` attribute, which is a JavaScript object. The `.style` object has attributes that can be used to read or set style properties for the DOM element. Any time we have selected a DOM element we can read or set the values of all CSS properties by referencing the property name. Here is an example:

**html**
```html
<button class="btn save">Save</button>
```

**css**
```css
.save {
    background: blue;
    color: white;
    font-size: 1.2rem;
    font-family: sans-serif;
}
.btn {
    padding: 0.2rem;
    border: 1px solid yellow;
    background: black;
    color: white;
}
```

**js**
```
let saveButton = document.querySelector('button.save');
console.log(saveButton.style.background); // Prints: "blue"
console.log(saveButton.style.fontSize); // Prints: "1.2rem"
console.log(saveButton.style.fontFamily); // Prints: "sans-serif"
console.log(saveButton.style.border); // Prints: "1px solid yellow"
console.log(saveButton.style.padding); // Prints: "0.2rem"
```

Looking at the HTML, CSS, and JS above, we can see that the `<button>` element has two classes applied to it: `.btn` and `.save`. These two classes define several properties for the visual presentation of the button. In the JavaScript part of the example, we select the `saveButton` using a standard `document.querySelector()` call. Once we have selected the button element we can access the `.style` attribute to read and print the CSS properties applied to this element. 

We could also change the values dynamically using JavaScript:

```js
saveButton.style.background = "red";
saveButton.style.color = "yellow";
```
These two lines of JavaScript would alter the background and text color of the button. We could set these style properties to any valid CSS value and they would override the existing style in the browser.

## Setting Styles in Bulk: `csstext`
As we can see in the example above, the `.style` attribute of a DOM element object is very useful for working with styles. But if we want to alter or read several styles all at once it can be a bit tedious to type it all out in separate lines of code. Fortunately, there is a `cssText` attribute on the `.style` object that allows for writing styles in one big chunk of text. Consider this example:

```js
let newItem = document.createElement('li');
newItem.style.cssText = "background:green; color: white; font-family: sans-serif; border: 1px solid blue;";
```

Using the `cssText` property allows us to set many style properties with a more-or-less normal definition. It must all be compressed into a string, but we could use a template literal to allow for a more eye pleasing presentation in the code (and easier dynamic population of any values we've calculated for styles).

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