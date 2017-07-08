# Selecting Elements

In order to work with the content of an HTML file, it's important to be able to retrieve specific elements and work with them in JavaScript. Most of the commands we can use to work with elements of the DOM are methods of the `document` object. The `document` object contains all sorts of properties that can tell us about the HTML, and it provides methods that can be used to perform actions on the HTML. The set of methods we will focus on for this section are those concerned with selecting elements out of the DOM.

## Query Selectors
In modern ECMAScript, the `document` object provides two key methods to find and retrieve elements from the DOM: `document.querySelector()` and `document.querySelectorAll()`. These two methods allow us to select DOM elements using CSS selectors. Here is an example of some HTML and JS that works together:

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





## Old Style Selectors

{% exercise %}
Define a problem.

{% initial %}
// initial code 

{% solution %}
// solution code

{% validation %}
assert(true), "Incorrect.");

{% endexercise %}