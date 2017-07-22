# Extra Practice

Remember: Learning to program takes practice! It helps to see concepts over and over, and it's always good to try things more than once. We learn much more the second time we do something. Use the exercises and additional self-checks below to practice.


## 1. Save Buttons
Review the code, then answer the questions below.

```js
let saveButtons = document.querySelectorAll('.save-button');

for (let button of saveButtons){
    button.addEventListener('click', function(event){
        let contentID = event.target.dataset.id;
        console.log(`Saving ${contentID}`);
    });
}
```
<quiz name="">
    <question>
        <p>What is <code>saveButtons</code> equal-to?</p>
        <answer correct>an Array-like collection of DOM elements selected by '.save-button'</answer>
        <answer>the first element in the DOM with the 'save-button' class</answer>
        <answer>a DOM element object</answer>
        <answer><code>undefined</code></answer>
        <explanation><code>saveButtons</code> contains an Array-like collection of DOM elements.</explanation>
    </question>
    <question>
        <p>Inside the <code>for</code> loop, what name is used to refer to each individual button element?</p>
        <answer><code>saveButtons[]</code></answer>
        <answer correct><code>button</code></answer>
        <answer><code>event</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>Inside the <code>for</code> loop, the <code>button</code> variable refers to each individual button element during each iteration of the loop.</explanation>
    </question>
    <question>
        <p>What will <code>event.target</code> refer to inside the event listener?</p>
        <answer>The handler function.</answer>
        <answer>The event listener itself.</answer>
        <answer correct>The button the user clicked.</answer>
        <answer><code>undefined</code></answer>
        <explanation>The <code>event.target</code> property will refer to the button element the user clicked.</explanation>
    </question>
    <question>
        <p>What event is being listened for?</p>
        <answer><code>mouseover</code></answer>
        <answer correct><code>click</code></answer>
        <answer><code>load</code></answer>
        <answer><code>DOMContentLoaded</code></answer>
        <explanation>The <code>click</code> event is being listened for.</explanation>
    </question>
    <question>
        <p>What attribute on the save button would have contained the <code>contentID</code>?</p>
        <answer><code>data-contentID</code></answer>
        <answer correct><code>data-id</code></answer>
        <answer><code>contentID</code></answer>
        <answer><code>ID</code></answer>
        <explanation>The <code>data-id</code> attribute would be accessible as <code>event.target.dataset.id</code>.</explanation>
    </question>
</quiz>










<div class="no-quiz">
     <h2>Visit Content Online</h2>
     <p> 
         The content on this page has been removed from your PDF 
         or ebook format. You may view the content by visiting
         this book online.
     </p>
</div>
