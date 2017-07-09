# Quiz: The Document Object Model

Try this self-check quiz to test your knowledge!

<quiz name="">
    <question>
        <p>The Document Object Model (DOM) is a hierarchy that most closely resembles what object?</p>
        <answer>a tower</answer>
        <answer>a spiderweb</answer>
        <answer correct>a tree</answer>
        <answer>a tournament bracket</answer>
        <explanation>The DOM uses a tree-like hierarchy to relate all of its nodes.</explanation>
    </question>
    <question>
        <p>Every node in the DOM represents what?</p>
        <answer>a link</answer>
        <answer>a section</answer>
        <answer>a view</answer>
        <answer correct>an HTML element</answer>
        <explanation>Every node in the DOM represents and HTML element.</explanation>
    </question>
    <question multiple>
        <p>What three relationships between nodes are key to the DOM hierarchy?</p>
        <answer correct>parent</answer>
        <answer correct>child</answer>
        <answer correct>sibling</answer>
        <answer>cousin</answer>
        <explanation>The three relationships between nodes in the DOM are: parent, child, and sibling.</explanation>
    </question>
    <question>
        <p>Which method selects the first matching element in the document?</p>
        <answer><code>document.querySelectorAll()</code></answer>
        <answer ><code>document.getElementsByClass()</code></answer>
        <answer correct><code>document.querySelector()</code></answer>
        <answer><code>document.getElementsByTagName()</code></answer>
        <explanation>The <code>document.querySelector()</code> method returns the first matching DOM element.</explanation>
    </question>
    <question>
        <p>Which command creates a new button?</p>
        <answer><code>let button = document.new('button');</code></answer>
        <answer><code>let button = document.createElement('<button>');</code></answer>
        <answer correct><code>let button = document.createElement('button');</code></answer>
        <answer><code>let button = document.makeElement('{button}');</code></answer>
        <explanation>The <code>let button = document.createElement('button');</code> command creates a new button.</explanation>
    </question>
    <question>
        <p>Which command adds the <code><button></code> we just created to the DOM?</p>
        <answer correct><code>document.body.appendChild(button);</code></answer>
        <answer><code>document.insert(button);</code></answer>
        <answer><code>window.appendChild(button);</code></answer>
        <answer><code>document.insertBefore(button);</code></answer>
        <explanation>The <code>document.body.appendChild(button);</code> command appends the button to the <code>body</code> of the document.</explanation>
    </question>
    <question multiple>
        <p>What can we accomplish by modifying a DOM element's <code>innerHTML</code> attribute?</p>
        <answer correct>Add child elements and content.</answer>
        <answer correct>Alter text content.</answer>
        <answer correct>Clear existing content.</answer>
        <answer>Modify parent element content.</answer>
        <answer>Add event listeners.</answer>
        <explanation>We cannot modify parent element content or add event listeners with <code>innerHTML</code>.</explanation>
    </question>
    <question>
        <p>What method allows us to add an attribute to a DOM element?</p>
        <answer><code>element.getAttribute()</code></answer>
        <answer><code>element.createAttribute()</code></answer>
        <answer correct><code>element.setAttribute()</code></answer>
        <answer><code>element.makeAttribute()</code></answer>
        <explanation>The <code>element.setAttribute()</code> method is used to create a new attribute on a DOM element (and also to alter an existing attribute).</explanation>
    </question>

    <question multiple>
        <p>Which are valid CSS property names in JavaScript?</p>
        <answer correct><code>fontFamily</code></answer>
        <answer><code>background-position</code></answer>
        <answer correct><code>marginTop</code></answer>
        <answer><code>font-weight</code></answer>
        <answer correct><code>background</code></answer>
        <explanation>Dashes are not allowed in JavaScript object attribute names, so they must be converted to camelCase.</explanation>
    </question>

    <question>
        <p>What does the <code>window.getComputedStyle()</code> method return?</p>
        <answer correct>A <code>style</code> object with all of the CSS properties affecting the visual display of the DOM element (including those inherited from parent elements).</answer>
        <answer>A <code>properties</code> object with some of the CSS properties affecting the visual display of the DOM element.</answer>
        <answer>An Array of the CSS properties affecting the visual display of the DOM element based on CSS files.</answer>
        <answer>A <code>style</code> object with only the CSS properties defined explicitly for the DOM element.</answer>
        <answer>text</answer>
        <explanation>The <code>window.getComputedStyle()</code> method returns a <code>style</code> object with all of the CSS properties affecting the visual display of the DOM element (including those inherited from parent elements).</explanation>
    </question>
    
    <question>
        <p>What prefix indicates that an HTML attribute is intended to store information for computing?</p>
        <answer><code>info-</code></answer>
        <answer><code>db-</code></answer>
        <answer correct><code>data-</code></answer>
        <answer><code>query-</code></answer>
        <answer><code>param-</code></answer>
        <explanation>The <code>data-</code> prefix indicates that an HTML attribute is intended to store information for computing.</explanation>
    </question>

    <question>
        <p>How can we access the data attributes of an HTML element from within JavaScript?</p>
        <answer><code>element.getData()</code></answer>
        <answer correct><code>element.dataset</code></answer>
        <answer><code>element.getAttribute()</code></answer>
        <answer><code>element.db</code></answer>
        <answer><code>element.fetchData()</code></answer>
        <explanation>Data stored in HTML data attributes is available in the <code>element.dataset</code> object.</explanation>
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
