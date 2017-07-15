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


## 2. Extending Classes
Review the code, then answer the questions below.

```js
class Vehicle {
    constructor(license='ES64EVA'){
        this.license = license;
    }
    move(direction){
        console.log(`Vehicle ${this.license} moves ${direction}`);
    }
    get description(){
        return `Vehicle ${this.license} is a shapeless carriage.`;
    }
    
}

class Car extends Vehicle {
    constructor(license, numAxles=2, numWheels=4){
        super(license);
        this.numAxles = 2;
        this.numWheels = 4;
    )
    
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
