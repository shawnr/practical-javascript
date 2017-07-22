# Extra Practice

Remember: Learning to program takes practice! It helps to see concepts over and over, and it's always good to try things more than once. We learn much more the second time we do something. Use the exercises and additional self-checks below to practice.


## 1. TODO
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
    <question multiple>
        <p>When is the <code>constructor()</code> method executed?</p>
        <answer>When we call <code>Road.constructor()</code>.</answer>
        <answer correct>When we create an instance of the <code>Road</code> class using the <code>new Road()</code> command.</answer>
        <answer>When we call <code>Road()</code> anywhere in our code.</answer>
        <answer>When the interpreter reads the <code>Road</code> Class definition.</answer>
        <explanation>The <code>constructor()</code> method is executed when we create a new instance of the <code>Road</code> class using the <code>new Road()</code> command.</explanation>
    </question>
    <question>
        <p>What is <code>cityRoad.lanes</code> equal to?</p>
        <answer><code>2</code></answer>
        <answer correct><code>4</code></answer>
        <answer><code>3</code></answer>
        <answer><code>0</code></answer>
        <explanation>The value of <code>cityRoad.lanes</code> is <code>4</code>.</explanation>
    </question>
    <question>
        <p>What is <code>countryRoad.sidewalk</code> equal to?</p>
        <answer><code>true</code></answer>
        <answer correct><code>false</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The value of <code>countryRoad.sidewalk</code> is <code>false</code>.</explanation>
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
