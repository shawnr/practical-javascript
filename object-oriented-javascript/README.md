# Object Oriented JavaScript

Prior to ECMAScript 6, JavaScript supported "object oriented"-like functionality, but it was difficult and clunky to emulate a real object oriented approach to writing code. For that reason, JavaScript mostly used functions and events to chain together features, which worked well enough but caused some consternation for developers used to operating in an object oriented context.

Some of the most popular languages in the world are object oriented programming languages: C++, Java, Python, Objective C, C#, etc. Although there are other popular programming paradigms, object oriented programming (often abbreviated as OOP) has been a major force in software development for several decades. It is a set of core principles and design concepts that has proven to be a useful way of thinking about information and functionality.

In this section we will learn more about OOP concepts and how we can use those concepts in our code. Keep in mind that the fundamental concepts behind OOP are not exclusive to JavaScript, so it is useful to know these concepts even beyond the realm of our browser-based code.

<div class="tip-box">

<h3>Prototype: Under the Hood</h3>

<p>In JavaScript, the way that Objects are implemented is with the <a href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes">"prototype mechanism"</a>. The <code>Object.prototype</code> attribute points to a template for each specific kind of Object in the system. This <code>prototype</code> is inherited by any Objects derived from a given template (for example: Number, Boolean, Date, etc.). The <code>prototype</code> provides the model for all the functionality these different Object types afford us.</p>

<p>We can create new Objects and then use them to create instances of those Objects, as described in object oriented programming theory, but the way this is implemented in JavaScript is via the <code>Object.prototype</code> mechanism. The <code>prototype</code> of any Object can be modified and changed, and the <code>prototype</code> continues to exist in spite of the new ECMAScript 6 syntax that makes it easier to write and use more conventional Classes in JavaScript. We do not dive deep in the <code>Object.prototype</code> in this book, but it is there to explore as we discover more sophisticated cases to solve.</p>

</div>


