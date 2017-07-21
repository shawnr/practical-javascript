# Handling Events

In our code so far, we have worried primarily about doing things. We have created variables, objects, classes, and more. We have looped and conditionaled (?) and generally directed the logic, timing, and actions our code takes in a somewhat linear manner. This is all well and good, but it's missing a crucial element to truly be useful to us as web developers.

In the real-world, our JavaScript code lives in the browser, where a user is viewing a web page. The user is going to scroll, click, select, fill in forms, and do all sorts of other things on that web page. We want our code to be the thing that makes all these interactions possible, and in order to do that, we must be able to do one specific thing: React to a user's input.

We have to know when the user scrolled, clicked, filled in a field, submitted a form, and much more. We need to know when our page has finished downloading and is ready for the user to interact with it. We might very well need to know when certain portions of our code are done with their processing and have caused something to change in the context of our application. 

In each of these cases, we can use built-in features of JavaScript to respond to [**Events**](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events). Events are signals that are emitted within the JavaScript context. There are many events that are triggered throughout a user's interaction with the web page: click events, scroll events, page load events, etc. These events always exist and they are always being emitted when the browser detects user interaction. But we must set up our JavaScript code to _listen_ for these events and respond to them.

We can use [the built-in events](https://developer.mozilla.org/en-US/docs/Web/Events) emitted by user interactions to effectively build interface elements, but we can also define our own events and use those to build even more complex systems that respond to changes in both user behavior and data. We could define an event, for example, that would update the interface with new data whenever a value in the system changes. Or we might define an event that would kick off a larger process, such as publishing a new content item.

<div class="tip-box">

<h2>Event-Driven Systems</h2>

<p>There is a whole world of thought about <a href="https://en.wikipedia.org/wiki/Event-driven_architecture">event-driven system architecture</a>, and many of those concepts are applicable to JavaScript. Events allow us to practice "loose coupling", which describes the practice of building systems that work together but which share few dependencies.</p> 

<p>For example, a content management system might have one component that is concerned with content authoring and managing editorial approval. That system might be complex and dynamic, but at some point it would trigger a "publish article" event. The publishing system need not know anything about the business logic of reviewing and approving content or the product needs of the content outside of the publishing formats. The publishing system could be an independent process that picks up the data at the right time and packages it for publishing in whatever formats are configured. Once the publishing operation is completed, the publishing system could emit a "article published successfully" event and the content management system could listen for that event in order to trigger the next step in the process.</p>

<p>In this example, the content management system and the publish system could be said to be "loosely coupled"&mdash;meaning that they have a small dependency on one another, but generally do their job autonomously. The event signals are sent and received by each individual component of the system, and each component is able to listen for and respond to relevant events.</p>

<p>Event-driven systems are all over the place. They are popular in games, in asynchronous communications utilities, and other systems that manage complex processes where system changes might come from many different sources.</p>

</div>


