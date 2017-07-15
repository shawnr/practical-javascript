# Extra Practice

Remember: Learning to program takes practice! It helps to see concepts over and over, and it's always good to try things more than once. We learn much more the second time we do something. Use the exercises and additional self-checks below to practice.


## 1. Creating Classes and Class Instances
Review the code, then answer the questions below.

```js
class Road {
    constructor(directions=['east','west'],sidewalk=true){
        this.directions = directions;
        this.numLanes = directions.length;
        this.sidewalk = sidewalk;
    }
}

let cityRoad = new Road(['north','north','south','south'], true);

let countryRoad = new Road(['east','west'], false);
```
<quiz name="">
    <question>
        <p>What is the name of the Class?</p>
        <answer><code>class</code></answer>
        <answer><code>constructor</code></answer>
        <answer correct><code>Road</code></answer>
        <answer><code>road</code></answer>
        <explanation>The name of the Class is <code>Road</code>.</explanation>
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
        <p>What is <code>foo</code> equal to?</p>
        <answer><code>42</code></answer>
        <answer correct><code>36</code></answer>
        <answer><code>15</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The variable <code>foo</code> is equal to <code>36</code>.</explanation>
    </question>
    <question>
        <p>What is <code>bar</code> equal to?</p>
        <answer><code>55</code></answer>
        <answer><code>19</code></answer>
        <answer correct><code>60</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The variable <code>bar</code> is equal to <code>60</code>.</explanation>
    </question>
    <question>
        <p>What is <code>baz</code> equal to?</p>
        <answer><code>6</code></answer>
        <answer><code>5</code></answer>
        <answer><code>42</code></answer>
        <answer correct><code>undefined</code></answer>
        <explanation>The variable <code>baz</code> is equal to <code>undefined</code> because we cannot multiply two Strings.</explanation>
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
