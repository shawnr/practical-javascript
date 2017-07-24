# Altering DOM Element Styles
Another task we perform often in our JavaScript programs is altering the visual styling of elements in the DOM. This allows us to create all sorts of interactive visual effects that can provide a compelling experience for the user. Although we can use the `setAttribute()` property on a DOM element to change the classes we have applied, there are other ways to modify styles either in groups or individually.

## The `element.style` Attribute

Each DOM element has a [`element.style` attribute](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style), which is a JavaScript object. The `element.style` object has attributes that can be used to read or set style properties for the DOM element. Any time we have selected a DOM element we can read or set the values of all CSS properties by referencing the property name. Here is an example:

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

Looking at the HTML, CSS, and JS above, we can see that the `<button>` element has two classes applied to it: `.btn` and `.save`. These two classes define several properties for the visual presentation of the button. In the JavaScript part of the example, we select the `saveButton` using a standard `document.querySelector()` call. Once we have selected the button element we can access the `element.style` attribute to read and print the CSS properties applied to this element. 

We could also change the values dynamically using JavaScript:

```js
saveButton.style.background = "red";
saveButton.style.color = "yellow";
```

These two lines of JavaScript would alter the background and text color of the button. We could set these style properties to any valid CSS value and they would override the existing style in the browser.

<div class="tip-box">

<h3>JS Mapping of CSS Properties</h3>

<p>JavaScript objects have attributes. Those attributes cannot be named with dashes. However, some CSS properties (<code>font-face</code>, <code>background-color</code>, <code>border-size</code>, etc.) have dashes in their names. So how do we reference these properties as part of the <code>element.style</code> object?</p>

<p>There is a mapping between CSS Property names and the names they are given as attributes of the <code>element.style</code> object. For the most part, the dashes are removed and the name is written in "camelCase", which is common in JavaScript. So <code>font-face</code> becomes <code>element.style.fontFace</code> and <code>background-color</code> becomes <code>element.style.backgroundColor</code>. <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Properties_Reference">A full chart of property name conversions can be found here.</a></p>

</div>



## Setting Styles in Bulk: `element.style.cssText`
As we can see in the example above, the `element.style` attribute of a DOM element object is very useful for working with styles. But if we want to alter or read several styles all at once it can be a bit tedious to type it all out in separate lines of code. Fortunately, there is a [`cssText` attribute](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style) on the `element.style` object that allows for writing styles in one big chunk of text. Consider this example:

```js
let newItem = document.createElement('li');
newItem.style.cssText = "background:green; color: white; font-family: sans-serif; border: 1px solid blue;";
```

Using the `cssText` attribute allows us to set many style properties with a more-or-less normal definition. It must all be compressed into a string, but we could use a template literal to allow for a more eye pleasing presentation in the code (and easier dynamic population of any values we've calculated for styles).

## Reading Computed Styles
Sometimes DOM elements are affected by styles not directly applied to them. Many CSS properties are inherited from parent elements, and it's very common to use CSS inheritance to our advantage as web developers and interface designers. Keeping things like font families and sizes consistent is core to providing a robust, pleasing interaction for users. But sometimes we need to know the "computed styles" of a DOM element.

We can use [the `window.getComputedStyle()` method](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle) to retrieve the computed styles that are applied to a specific DOM element. This method returns a `style` object very much like the `element.style` object we worked with previously. We can review the values of these properties and use them to make decisions about changes based on the exact styles the user sees applied to that element. Here is an example:

**html**
```html
<body style="font-weight: bold;">
    <p style="color: green;">Page content.</p>
</body>
```

**js**
```js
let paragraph = document.querySelector('p');
let computedStyle = window.getComputedStyle(paragraph);

console.log('Element style for font-weight: ' + paragraph.style.fontWeight); // prints empty string ("")
console.log('Computed style for font-weight: ' + computedStyle.fontWeight); // prints "bold"

console.log('Element style for color: ' + paragraph.style.color); // prints "green"
console.log('Computed style for color: ' + computedStyle.color); // prints "rgb(0,255,0)"
```

In this example we can see that the element style is restricted to styles explicitly applied to the element, and the properties use the same definition we specified in our stylesheets or HTML. However, the computed style returns the actual style being applied, even if it was inherited from a parent element. The computed style also converts synonyms and shortcuts (such as "green") to their computed value (in this case, `rgb(0,255,0)`).

Understanding which set of styles we want to work with, defined or computed, is important to getting the most out of our efforts. Regardless of which values we need, we can easily find them, work with them, and alter them using JavaScript.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section. The exercises in this section all assume the following HTML. Please write JavaScript as if it is attached to this HTML snippet:

```html
<button class="btn save">Save Item</button>
```

{% exercise %}
Given the HTML above, write JavaScript to change the styles to be: background: green, padding: 0.2rem, color: white, 
border: solid 1px yellow, border-radius: 4px.


{% initial %}
// Select the button from the DOM using document.querySelector(). 
let saveButton = ;

// Alter styles using either Element.style or Element.style.cssText.



{% solution %}
// Select the button from the DOM using document.querySelector(). 
let saveButton = document.querySelector('button');

saveButton.style.backgroundColor = 'green';
saveButton.style.padding = '0.2rem';
saveButton.style.color = 'white';
saveButton.style.border = 'solid 1px yellow';
saveButton.style.borderRadius = '4px';


{% validation %}
assert(saveButton.style.color, "Incorrect.");

{% context %}

function saveItem(id){
    if (id=="12234"){
        return true;
    } else {
        return false;
    }
}
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
        this.dataset = {};
        this.dataset.saved = false;
        this.dataset.id = '12234';
        
        this.style.cssText = '';            
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