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
</quiz>

<div class="no-quiz">
     <h2>Visit Quiz Online</h2>
     <p> 
         The quiz on this page has been removed from your PDF 
         or ebook format. You may take the quiz by visiting
         this book online.
     </p>
</div>
