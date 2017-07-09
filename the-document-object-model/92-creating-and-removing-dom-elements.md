# Creating and Removing DOM Elements

Now that we've explored how to select and retrieve elements from the DOM, we will move on to how to modify these elements. Modifying elements in the DOM, or adding/removing elements to/from the DOM, is crucial to creating a responsive experience for users. Users expect that if they interact with a page it will change: links will light up, buttons will click down, text will change, notifications will come and go, and their actions will have an effect.

Our pages should engage the user at all times in ways that are meaningful, predictable, and regular. If a user clicks "save" there should be suitable feedback to let the user know that the item has been saved. This helps the user understand what has happened and it matches what the user anticipated would happen. The next time the user clicks "save" the same interaction should unfold. This shows regularity in the interface. 

Of course, making broad statements about how things _should_ happen on a web page is one thing. Building those features is often another matter entirely. Let's take a look at how we can begin that task.

For the following examples, refer to this HTML markup for a contact list:

```html
<ul id="contact-list">
    <li class="contact">
        <p class="name">Grace Hopper</p>
        <p class="phone">555-1234</p>
        <p class="email"><a href="mailto:grace@example.com">grace@example.com</a></p>
        <p class="address">123 Fake St.</p>
        <p class="city">Anytown</p>
        <p class="state">XZ</p>
    </li>
    <li class="contact">
        <p class="name">Bill Joy</p>
        <p class="phone">555-8754</p>
        <p class="email"><a href="mailto:bill@example.com">bill@example.com</a></p>
        <p class="address">42 Nowhere Ct.</p>
        <p class="city">Somewhere</p>
        <p class="state">ZY</p>
    </li>
    <li class="contact">
        <p class="name">Katherine Johnson</p>
        <p class="phone">555-3323</p>
        <p class="email"><a href="mailto:k8@example.com">k8@example.com</a></p>
        <p class="address">555 Secret Place</p>
        <p class="city">Nowhere</p>
        <p class="state">DV</p>
    </li>
</ul>
```

## Adding Elements to the DOM
It's often necessary to add elements into the DOM. We can do this using a few different techniques. Often it's best to combine some techniques in order to maximize efficiency. Here is an example where we add a `contact` object to the list in the HTML example above.

```js
function addContact(contactObj){
    // Set up a template literal to populate the data into an HTML structure.
    let contactContent =   `<p class="name">${contactObj.name}</p>
                            <p class="phone">${contactObj.phone}</p>
                            <p class="email"><a href="mailto:${contactObj.email}">${contactObj.email}</a></p>
                            <p class="address">${contactObj.address}</p>
                            <p class="city">${contactObj.city}</p>
                            <p class="state">${contactObj.state}</p>`;
    
    // Make a new list item (`li`) to contain the contact content.
    let newContactLI = document.createElement('li');
    newContactLi.innerHTML = contactContent;
    
    // Select the `ul` containing all the contacts.
    let contactList = document.querySelector('#contact-list');
    
    // Append the new list item.
    contactList.appendChild(newContactLI);
}    
``` 
In this example we can see a couple different approaches to creating new DOM elements and adding them to the DOM. First, we use a template literal that contains all the HTML markup populated with our data from `contactObj`, which is passed into this function as a parameter. After we have made the `contactContent` template literal, we then create the `newContactLI` object using the [`document.createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement) method. This method creates a new DOM element, which in this case is called `newContactLI`, but it does _not_ add that element to the DOM (we do that later in the example). 

Once we've created the `newContactLI` object, we set `newContactLI.innerHTML` equal to `contactContent`. This populates the `newContactLI` object with our template literal. The `innerHTML` attribute on any DOM element contains all of the HTML within that element. In this case, our new list item contains no HTML. It's the equivalent of: `<li></li>`. Once we set the element's `innerHTML` value to our `contactContent` template literal, the `innerHTML` is populated directly.

Now that we have our new list item all populated with content, we can add it to the contact list in the DOM. The new list item is not visible in our browser until we append it to some element in the DOM, so this step is absolutely necessary.

To append the new list item to the contact list, we must first select the unordered list containing the contacts (with the ID `#contact-list`). We do that and call it `contactList` in our code. Next, we use the [`appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild) method of DOM elements to append the new contact list item to the contact list.

Although we often get by using just a few of the features of DOM elements, it's worthwhile to explore [the full set of properties and methods available on DOM element objects](https://developer.mozilla.org/en-US/docs/Web/API/element). This includes properties like `scrollHeight` and `className`, which can be used when processing different types of interaction. There are also additional methods that can accommodate our computing needs such as `insertBefore()`, which inserts a new DOM element object _before_ the selected object. 

The trickiest part of creating new DOM elements is making decisions about the best way to build up the HTML involved. It's entirely possible to create elements and set all of their attributes using specific JavaScript commands. However, it's often much quicker and easier to maintain to populate large HTML structures using template literals and then drop that HTML into a container element. There's no single correct way to approach this task, so experiment with all the ways of adding elements into the DOM to get a feeling for what works.

## Removing Elements from the DOM
Removing elements from the DOM is also possible using a variety of techniques. As with adding elements to the DOM, there is no single correct approach, and we will develop preferences for what works in different situations. A simple way of removing elements from the DOM is to select their parent element and then set the `innerHTML` value to an empty string (`''`). Here's an example of removing all of the list items from the `#contacts-list` element using `innerHTML`:

```js
// Select the unordered list containing contacts.
let contactsList = document.querySelector('#contacts-list');

// Remove all list items (and their content) using the `innerHTML` property.
contactsList.innerHTML = '';
```

By setting the `innerHTML` of the `contactsList` object to `''`, we have removed all of the list items, too. This is easy and clean, but it is also a fairly blunt way of removing a DOM element. We often need a more precise or limited way of removing elements from the DOM. For that, we can use the [`remove()`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/remove) method of each DOM element object. Here is an example:

```js
let firstContactItem = document.querySelector('.contact');
firstContactItem.remove()
```

This example selects the first contact item with the `.contact` class and removes it from the DOM. It uses the `remove()` method to accomplish this goal. Although this example is a bit glib, it illustrates how easy it is to remove an element from the DOM once we've selected it. We often have the case where we have a specific element object to work with, and in the next section we will explore more about how to respond to events that are triggered by individual DOM elements. 


## Exercises
Please try working these exercises to practice some of the skills we've learned in this section. The exercises in this section all assume the following HTML. Please write JavaScript as if it is attached to this HTML snippet:

```html
<ul id="search-results">
    <li class="result book">
        <p class="title">Dune <span class="format">Book</span></p>
        <p class="year">1965</p>
        <ul class="actions">
            <li><a href="#save">Save</a></li>
            <li><a href="#share">Share</a></li>
            <li><a href="#report">Report</a></li>
        </ul>
    </li>
    <li class="result movie">
        <p class="title">Dune <span class="format">Movie</span></p>
        <p class="year">1984</p>
        <ul class="actions">
            <li><a href="#save">Save</a></li>
            <li><a href="#share">Share</a></li>
            <li><a href="#report">Report</a></li>
        </ul>
    </li>
    <li class="result tv">
        <p class="title">Dune <span class="format">Television</span></p>
        <p class="year">2000</p>
        <ul class="actions">
            <li><a href="#save">Save</a></li>
            <li><a href="#share">Share</a></li>
            <li><a href="#report">Report</a></li>
        </ul>
    </li>
</ul>
```

{% exercise %}
Select the <code>search-results</code> list and make it available in a variable called <code>resultsList</code>. Use <code>document.querySelector()</code>. Create a new list item with the following info:<br>
<ul>
    <li>Title: Children of Dune</li>
    <li>Format: Television</li>
    <li>Year: 2003</li>
</ul><br>
Once you've finished populating the Append the new list item as a new child at the end of the <code>resultsList</code>.

{% initial %}
// Set `resultsList` equal to the DOM element for the search-results list. 

// Create a new list item called `newLI`

// Set innerHTML of new list item to match HTML structure with new data specified above.

// Append `newLI` to the `resultsList`


{% solution %}
// Set `resultsList` equal to the DOM element for the search-results list. 
let resultsList = document.querySelector('#search-results');

// Create a new list item called `newLI`
let newLI = document.createElement('li');

// Set innerHTML of new list item to match HTML structure with new data specified above.
newLI.innerHTML = `
    <p class="title">Children of Dune <span class="format">Television</span></p>
        <p class="year">2003</p>
        <ul class="actions">
            <li><a href="#save">Save</a></li>
            <li><a href="#share">Share</a></li>
            <li><a href="#report">Report</a></li>
        </ul>`;
// Append `newLI` to the `resultsList` as a new child element.
resultsList.appendChild(newLI);

{% validation %}
assert(resultsList.children.length==1, "Incorrect.");

{% context %}
class MockDoc {
    querySelector(q){
        if (q == "#search-results"){
            return new MockElem("UL");
        } else {
            return null;
        }
    }
    createElement(type){
        if (type == "li") {
            return new MockElem("LI");
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
}
var document = new MockDoc();

{% endexercise %}
