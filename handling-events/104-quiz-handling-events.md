# Quiz: Handling Events

Try this self-check quiz to test your knowledge!

<quiz name="">
    <question>
        <p>What can we attach to DOM elements in order to respond to events in the system?</p>
        <answer>Event Handlers</answer>
        <answer correct>Event Listeners</answer>
        <answer>Event Processors</answer>
        <answer>Event Coordinators</answer>
        <explanation>We create Event Listeners, which are attached to DOM elements and respond to specific event signals dispatched to the system.</explanation>
    </question>
    <question>
        <p>What method do we use to create an event listener?</p>
        <answer><code>element.makeEventListener()</code></answer>
        <answer><code>element.listen()</code></answer>
        <answer><code>element.on()</code></answer>
        <answer correct><code>element.addEventListener()</code></answer>
        <explanation>The command <code>element.addEventListener()</code> is the preferred method for creating a new event listener.</explanation>
    </question>
    <question>
        <p>The following example uses what type of function to handle an event? <br><br><code>element.addEventListener('click', function(event){});</code></p>
        <answer>named function</answer>
        <answer correct>anonymous function</answer>
        <answer>inline function</answer>
        <answer>arrow function</answer>
        <explanation>This example uses an anonymous function.</explanation>
    </question>
    <question>
        <p>What property on the <code>event</code> object contains the DOM object that invoked the event?</p>
        <answer><code>event.element</code></answer>
        <answer><code>event.source</code></answer>
        <answer correct><code>event.target</code></answer>
        <answer><code>event.invoker</code></answer>
        <explanation>The <code>event.target</code> property is a reference to the DOM object that invoked the event.</explanation>
    </question>
    <question>
        <p>Why is the <code>event.preventDefault()</code> command used?</p>
        <answer>To prevent the setting of default data values in the database.</answer>
        <answer correct>To prevent the execution of default actions in response to an event trigger.</answer>
        <answer>To enforce the submission of a form.</answer>
        <answer>To stop execution of all code.</answer>
        <explanation>The <code>event.preventDefault()</code> command prevents the execution of default actions in response to an event trigger or signal.</explanation>
    </question>
    <question>
        <p>Which event trigger indicates the DOM has finished loading and processing?</p>
        <answer correct><code>DOMContentLoaded</code></answer>
        <answer><code>DOMReady</code></answer>
        <answer><code>DOMFinished</code></answer>
        <answer><code>DocumentReady</code></answer>
        <explanation>The <code>DOMContentLoaded</code> event is dispatched when the HTML has been downloaded and the DOM has been processed.</explanation>
    </question>
</quiz>

<div class="no-quiz">
     <h2>Visit Quiz Online</h2>
     <p> 
         The quiz on this page has been removed from your PDF 
         or ebook format. You may take the quiz by visiting
         this book online.
     </p>
</div>
