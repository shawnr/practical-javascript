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
Please try working these exercises to practice some of the skills we've learned in this section.The exercises in this section all assume the following HTML. Please write JavaScript as if it is attached to this HTML snippet:

```html
<button class="btn save" data-id="12234" data-saved="false">Save Item</button>
```

{% exercise %}
Given the HTML above, write JavaScript to change the <code>data-saved</code> attribute to be <code>true</code> and read the <code>data-id</code> attribute to use in the <code>saveItem()</code> function.


{% initial %}
// Select the button from the DOM using document.querySelector(). 
let saveButton = 

// Alter the `data-saved` attribute to be 'true'.

// Use the provided `saveItem()` function to save the item.
// This function requires the item ID.

let saveSuccess = saveItem('Item ID goes here.');


{% solution %}
// Select the button from the DOM using document.querySelector(). 
let saveButton = document.querySelector('button');

// Alter the `data-saved` attribute to be `true`.
saveButton.dataset.saved = true;

// Use the provided `saveItem()` function to save the item.
// This function requires the item ID.

let saveSuccess = saveItem(saveButton.dataset.id);


{% validation %}
assert(saveButton.dataset.saved==true, "Incorrect.");

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