# Detecting Document Load Events

Early in this book we discussed the ways in which we [attach JavaScript to a web page](/basic-syntax/41-adding-javascript-to-an-html-file.md). We discussed the fact that we prefer to use external JavaScript files that are linked with `<script>` tags, and we mentioned that we should use either the `async` or `defer` attributes to prevent our JavaScript from "blocking" the load of other page assets. 

Since the web is a dynamic place, and different resources for a page could be coming from all over the world, we can never know for sure how long it will take for a user to receive all of the page resources or how long it will take to parse everything on the user's unique hardware. There is no certainty of order of download for most page resources, and it's completely possible for unexpected thing to happen during the load process. It is possible, and sometimes likely, that your JavaScript file will finish downloading and begin processing before the HTML of your page has completed downloading.

As we've been manipulating the DOM and adding listeners to DOM elements, it may have occurred to us that in some situations we could receive errors if our JavaScript were running before the HTML of the page had actually finished downloading. In general, it is not safe to perform operations on the HTML of our web pages before the file has been completely downloaded and parsed into the DOM.

Luckily, there is a way of knowing when the DOM has finished loading the HTML content of the page.

## The `DOMContentLoaded` Event

As we mentioned in the previous section, there are many events that are triggered by default in the process of viewing a web page. These events are being handled by default actions

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Define a problem.

{% initial %}
// initial code 

{% solution %}
// solution code

{% validation %}
assert(true), "Incorrect.");

{% endexercise %}