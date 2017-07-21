# Extra Practice

Remember: Learning to program takes practice! It helps to see concepts over and over, and it's always good to try things more than once. We learn much more the second time we do something. Use the exercises and additional self-checks below to practice.


## 1. Selecting and Adding DOM Elements
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
        <p>To set the <code>menuItems</code> variable equal to the collection of menu items in the subnav, what line of code would work?</p>
        <answer><code>let menuItems = document.querySelector('.page-title');</code></answer>
        <answer correct><code>let menuItems = document.querySelectorAll('.menu-item');</code></answer>
        <answer><code>let menuItems = document.getElementById('#subnav .menu-item');</code></answer>
        <answer ><code>let menuItems = document.querySelector('#subnav .menu-item');</code></answer>
        <explanation>The <code>menuItem</code> variable must be populated using a command that will select all of the matching elements in the DOM.</explanation>
    </question>
    <question>
        <p>What do we call objects like <code>menuItems</code> from the previous example?</p>
        <answer>DOM Element Lists</answer>
        <answer>Objects</answer>
        <answer correct>Array-like Objects</answer>
        <answer>Arrays</answer>
        <explanation>The <code>menuItems</code> variable contains the result of a <code>document.querySelectorAll()</code> call. That command returns an <i>Array-like Object</i> that can be iterated over but which has special functions, too.</explanation>
    </question>
    <question>
        <p>
            What would the results of this additional code be?<br>
            <code>
            let subnavUL = document.querySelector('#subnav');
            let newMenuItem = document.createElement('li');
            newMenuItem.innerHTML = '<a href="#">Contact Us</a>';
            newMenuItem.setAttribute('class', 'menu-item');
            subnavUL.appendChild(newMenuItem);
            </code>
        </p>
        <answer>The menu items in the <code>#subnav</code> list would be replaced with a new one.</answer>
        <answer correct>A new menu item with a "Contact Us" link would be added to the <code>#subnav</code> list.</answer>
        <answer>A new menu item with the "active" class would be added to the <code>#subnav</code> list.</answer>
        <answer>The <code>#subnav</code> list would be removed.</answer>
        <explanation>A new menu item with a "Contact Us" link would be added to the <code>#subnav</code> list.</explanation>
    </question>
    <question multiple>
        <p>What commands would select the <code>#subnav</code> element and set it equal to <code>subnavUL</code>?</p>
        <answer><code>let subnavUL = document.querySelector('.subnav');</code></answer>
        <answer correct><code>let subnavUL = document.querySelector('#subnav');</code></answer>
        <answer><code>let subnavUL = document.getElementById('#subnav');</code></answer>
        <answer correct><code>let subnavUL = document.getElementById('subnav');</code></answer>
        <explanation>There are two primary ways to select using the element ID from the DOM.</explanation>
    </question>
</quiz>


## 2. Modifying DOM Elements
Review the HTML code, then answer the questions below.

```html
<div id="item-123" class="content-item-wrapper">
    <h3 class="item-title">Magnificent Search Result</h3>
    <p class="item-description">Some helpful description about this search result.</p>
    <ul id="item-actions">
        <li class="action save"><a href="#">Save</a></li>
        <li class="action share"><a href="#">Share</a></li>
    </ul>
</div>  
```

<quiz name="">
    <question multiple>
        <p>How could we select <i>just</i> the content item wrapper element?</p>
        <answer><code>let contentItemWrapper = document.querySelector('.item-123');</code></answer>
        <answer correct><code>let contentItemWrapper = document.getElementById('item-123');</code></answer>
        <answer correct><code>let contentItemWrapper = document.querySelector('#item-123');</code></answer>
        <answer><code>let contentItemWrapper = document.getElementsByTagName('div');</code></answer>
        <explanation>There are several ways to select elements from the DOM and each can be used according to the context and needs of the program.</explanation>
    </question>
    <question>
        <p>Which command would select the "save" list item from inside the <code>contentItemWrapper</code> selected in the previous example?</p>
        <answer correct><code>let saveItem = contentItemWrapper.querySelector('.save');</code></answer>
        <answer><code>let saveItem = document.querySelectorAll('.save');</code></answer>
        <answer><code>let saveItem = document.getElementById('#item-actions .save');</code></answer>
        <answer ><code>let saveItem = document.querySelectorAll('#item-actions.save');</code></answer>
        <explanation>The <code>saveItem</code> variable may be populated using a query inside the <code>contentItemWrapper</code> DOM element.</explanation>
    </question>
    <question>
        <p>Which line of code would alter the class attribute on the <code>saveItem</code> element to indicate that the item has been saved?</p>
        <answer><code>saveItem.setAttribute('id', 'saved');</code></answer>
        <answer><code>saveItem.style.background = "#aa0000";</code></answer>
        <answer><code>saveItem.removeAttribute('class');</code></answer>
        <answer correct><code>saveItem.setAttribute('class', 'action saved');</code></answer>
        <explanation>The <code>saveItem</code> element makes the <code>setAttribute()</code> method available for modifying attributes.</explanation>
    </question>
    <question>
        <p>Which command would select the "share" list item from the <code>contentItemWrapper</code> element?</p>
        <answer><code>let shareItem = contentItemWrapper.querySelector('p.share');</code></answer>
        <answer><code>let shareItem = contentItemWrapper.querySelector('#item-actions.action.share');</code></answer>
        <answer><code>let shareItem = contentItemWrapper.querySelector('.action .share');</code></answer>
        <answer correct><code>let shareItem = contentItemWrapper.querySelector('.action.share');</code></answer>
        <explanation>The <code>shareItem</code> can be selected using <code>contentItemWrapper.querySelector()</code> with the correct CSS selector.</explanation>
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
