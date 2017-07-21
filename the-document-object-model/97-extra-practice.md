# Extra Practice

Remember: Learning to program takes practice! It helps to see concepts over and over, and it's always good to try things more than once. We learn much more the second time we do something. Use the exercises and additional self-checks below to practice.


## 1. Selecting DOM Elements
Review the HTML code, then answer the questions below.

```html
<div id="content">
    <ul id="subnav">
        <li class="menu-item"><a href="#">Home</a></li>
        <li class="menu-item active"><a href="#">Archive</a></li>
        <li class="menu-item"><a href="#">About Us</a></li>
    </ul>
    <h1 class="page-title">Archive of Posts</h1>
    <p>Use this archive listing to find old posts.</p>
</div>  
```
<quiz name="">
    <question multiple>
        <p>What line(s) of code would select the <code>H1</code> title of this page?</p>
        <answer correct><code>let pageTitle = document.querySelector('.page-title');</code></answer>
        <answer><code>let pageTitle = document.getElementById('#page-title');</code></answer>
        <answer correct><code>let pageTitle = document.querySelector('h1');</code></answer>
        <answer correct><code>let pageTitle = document.getElementByTagName('h1');</code></answer>
        <explanation>There are several ways to select elements from the DOM and each can be used according to the context and needs of the program.</explanation>
    </question>
    <question>
        <p>The <code>cityRoad</code> variable is a(n) ________ of the <code>Road</code> class.</p>
        <answer>attribute</answer>
        <answer>parameter</answer>
        <answer>element</answer>
        <answer correct>instance</answer>
        <explanation>The <code>cityRoad</code> variable is an <i>instance</i> of the <code>Road</code> class.</explanation>
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
