# The Document Object Model
The [Document Object Model (DOM)](https://en.wikipedia.org/wiki/Document_Object_Model) is the conceptual model used to represent an HTML document in the browser. JavaScript has built-in functionality to inspect, read, and modify every element in an HTML document using DOM-specific tools such as `document.querySelector()` and `element.addChild()`. There are many of these tools that we will use to interact with the DOM as we write our JavaScript programs.

The DOM defines the way that browsers understand the structure of HTML documents. It is a tree-like hierarchy that starts with a `document` node, then has one `html` node, and then branches out to `head` and `body` nodes. Here is an illustration of what the DOM generally "looks" like in diagram form:


