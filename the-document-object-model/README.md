# The Document Object Model
The [Document Object Model (DOM)](https://en.wikipedia.org/wiki/Document_Object_Model) is the conceptual model used to represent an HTML document in the browser. JavaScript has built-in functionality to inspect, read, and modify every element in an HTML document using DOM-specific tools such as `document.querySelector()` and `element.addChild()`. There are many of these tools that we will use to interact with the DOM as we write our JavaScript programs.

The DOM defines the way that browsers understand the structure of HTML documents. It is a tree-like hierarchy that starts with a `document` node, then has one `html` node, and then branches out to `head` and `body` nodes. Here is an illustration of what the DOM generally "looks" like in diagram form:

![The Document Object Model (DOM) by Birger Eriksson](/images/dom-model.png)

<caption>_The Document Object Model (DOM) by [Birger Eriksson](https://en.wikipedia.org/wiki/File:DOM-model.svg)_</caption>

In JavaScript, we can use different commands to traverse the DOM's tree hierarchy in order to access any information contained within the HTML document. This makes it possible to read and interpret information, to grab sections of a document and alter them, to add elements to the document, or to remove them. It is not uncommon for a JavaScript program to spend considerable time reading data from a document's elements and their attributes, writing new elements into the document, or modifying the class name or textual content of elements. 

Using the DOM standard tools, JavaScript programs can also alter the CSS attributes of a given element. This means that JavaScript can be used in conjunction with HTML and CSS to create very dynamic visual representations of HTML content. Elements can be made to move, take on different styles, perform various functions, and much more. 

As an example, we can consider the following snippets of JavaScript, CSS, and HTML.

```html
<button class="btn save">Save Item</button>
```

``` css
.save {
    background: blue;
    color: white;
    content: 'Save Item';
}
.saved {
    background: blue;
    color: yellow;
    content: 'Saved!';
}
```

```js
let saveButtons = document.querySelectorAll('.btn .save');
saveButtons.forEach(function(button){
    button.addEventListener('click', function(event){
        event.target.setAttribute('class', 'btn saved');
        event.target.setAttribute('disabled', true);
    });
});
```

We will dive deeper into how each part of this code works over the course of the next few sections of this book, but for now it's useful to see that we have all three parts of our web technology trifecta at play: HTML, CSS, and JavaScript.







