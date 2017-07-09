# Selecting Elements

In order to work with the content of an HTML file, it's important to be able to retrieve specific elements and work with them in JavaScript. Most of the commands we can use to work with elements of the DOM are methods of the `document` object. The `document` object contains all sorts of properties that can tell us about the HTML, and it provides methods that can be used to perform actions on the HTML. The set of methods we will focus on for this section are those concerned with selecting elements out of the DOM.

## Query Selectors
In modern ECMAScript, the `document` object provides two key methods to find and retrieve elements from the DOM: [`document.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) and [`document.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll). These two methods allow us to select DOM elements using CSS selectors. Here is an example of some HTML and JS that works together:

**html**
```
<section id="profile">
    <p class="image-wrapper"><img src="user.jpg" alt="User Profile Image"></p>
    <p class="bio">Some information about the user.</p>
    <ul id="profile-actions">
        <li><a href="#edit">Edit</a></li>
        <li><a href="#settings">Settings</a></li>
    </ul>
</section>
```

**js**
```
// Select the first matching element
let profileSection = document.querySelector('#profile');
let profileBio = document.querySelector('p.bio');
profileBio.innerHTML = 'Updated text about the user.' // Updates content of user bio.

// Select multiple elements
let profileActions = document.querySelectorAll('ul#profile-actions li');
for (action of profileActions){
    console.log(action.innerHTML); // Outputs link tag for each action item.
});
```

As we can see in this example, we have HTML for a user profile page. There is a section for the profile, and that section contains several other elements. In the JavaScript, we can see how the `document.querySelector()` method can be used to select one element at a time (the _first_ matching element). This is handy in many cases, but we can also use `document.querySelectorAll()` to select _all_ of the elements matching our CSS selector. We can see that the `profileActions` variable is populated with a `document.querySelectorAll()` command, so it is equal to the entire set of results matching the CSS selector query. If we loop through those results using a standard `for ... of` loop, we can see that each element has been retrieved.

These two commands can leverage the full power of [CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors). This means that we can use very complex syntax to define specific, dynamic, and highly customized queries. We can use everything we know about selecting elements for visual styling with CSS in order to enhance our pages. This is powerful stuff.

## Old Style Selectors
As with so many older features of JavaScript, old style DOM selectors are still functional and we still run across them in code. They can be used to select based on more fundamental properties of elements, which can sometimes be convenient. These commands are still provided as methods on the `document` object. They are:

* [`document.getElementById()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) &ndash; Fetches the one element with the given ID (note: do not supply a "`#`" when using this method).
* [`document.getElementsByClassName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName) &ndash; Fetches an Array-like set of elements that match the given Class name (note: do not supply a "`.`" when using this method).
* [`document.getElementsByTagName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName) &ndash; Fetches an Array-like set of elements that match the given HTML Tag name.

These can be used like we would expect, given the descriptions above. Here is an example:

**html**
```
<section id="profile">
    <p class="image-wrapper"><img src="user.jpg" alt="User Profile Image"></p>
    <p class="bio">Some information about the user.</p>
    <ul id="profile-actions">
        <li><a href="#edit">Edit</a></li>
        <li><a href="#settings">Settings</a></li>
    </ul>
</section>
```

**js**
```
// Select the first matching element
let profileSection = document.getElementById('profile');
let profileBio = document.getElementsByClassName('bio');
// Note how the index must be used below due to the results of `getElementsByClassName()`
profileBio[0].innerHTML = 'Updated text about the user.' // Updates content of user bio.

// Note that the selector below would match all `li` elements in the entire page.
let profileActions = document.getElementsByTagName('li');
for (action of profileActions){
    console.log(action.innerHTML); // Outputs link tag for each action item.
});
```
The code in this example does the exact same thing as the code in the previous example. In cases where we control the HTML entirely ourselves, it is not too bad to write code using these legacy selectors. We can use very specific Class and ID names to identify the HTML elements we need to work with. It can be a bit clunky to work with the older style selectors, but we can get the job done.

<div class="tip-box">

<h3>The Perils of Rigid Naming</h3>

<p>Part of the strength of CSS is that we can write selectors that are general enough to be very useful, but specific enough to perform the tasks we need. There has been a lot of thought put into how we can select elements within a DOM, and that thought has been expressed as the CSS Selector Syntax. For example, we can easily write selectors to select every other row in a table, every fifth item in a list, or diagonal elements in a grid. The CSS Selector language is very powerful, and without it, we become very rigid in how we name and structure elements.</p>

<p>When we rely entirely on explicit ID or Class names, our code becomes more fragile. There is more chance of conflict when developers change the names of IDs or Classes to suit the needs of either visual styling or interactivity. It becomes tempting to come up with complex naming schemes to differentiate between "functional" names and "design" names: classes that are found and used by JS versus classes found and used by CSS. For many years, developers struggled to have easier ways to select elements in the DOM.</p>

<p>From that struggle was born great tools like jQuery, which became the dominant JavaScript toolset for many years. Now that these features have become part of the standard JavaScript library, it's less necessary to always use a third-party module to make things more convenient. We can now leverage the full power of CSS Selectors from within JavaScript, and the world is a better place.</p>

</div>

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
Select the <code>search-results</code> list and make it available in a variable called <code>resultsList</code>. Use <code>document.querySelector()</code>.

{% initial %}
// Set `resultsList` equal to the DOM element for the search-results list. 

{% solution %}
// solution code
let resultsList = document.querySelector('#search-results');

{% validation %}
assert(resultsList, "Incorrect.");

{% context %}
class MockDoc {
    querySelector(q){
        if (q == "#search-results"){
            return true;
        } else {
            return false;
        }
    }
}
var document = new MockDoc();

{% endexercise %}

{% exercise %}
Use <code>document.querySelectorAll()</code> to select each of the result list items. Make this available as the variable `resultItems`.

{% initial %}
// Set `resultItems` equal to the DOM elements for each item in the search results list. 

{% solution %}
// solution code
let resultItems = document.querySelectorAll('#search-results .result');

{% validation %}
assert(resultItems, "Incorrect. Check your CSS selector.");

{% context %}
class MockDoc {
    querySelectorAll(q){
        if ((q == ".result") ||
            (q == "#search-results .result") ||
            (q == "li.result") ||
            (q == "#search-results li.result")){
            return true;
        } else {
            return false;
        }
    }
}
var document = new MockDoc();

{% endexercise %}