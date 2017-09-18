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
        <p>What is <code>cityRoad.numLanes</code> equal to?</p>
        <answer><code>2</code></answer>
        <answer correct><code>4</code></answer>
        <answer><code>3</code></answer>
        <answer><code>0</code></answer>
        <explanation>The value of <code>cityRoad.numLanes</code> is <code>4</code>.</explanation>
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
        this.numAxles = numAxles;
        this.numWheels = numWheels;
    }
    move(direction){
        return `Vehicle ${this.license} rolls ${direction}`;
    }
    get description(){
        return `Vehicle ${this.license} is a car with ${this.numAxles} axles and ${this.numWheels} wheels.`;
    }
}
class Airplane extends Vehicle {
    constructor(license, numWings=2, numPropellers=1){
        super(license);
        this.numWings = numWings;
        this.numPropellers = numPropellers;
    }
    move(direction){
        return `Vehicle ${this.license} flies ${direction}`;
    }
    get description(){
        return `Vehicle ${this.license} is an airplane with ${this.numWings} wings and ${this.numPropellers} propellers.`;
    }
}

let myCar = new Car('HOTWLZ1');

let myPlane = new Airplane('FLYIN1', 4);
    
```
<quiz name="">
    <question>
        <p>What is the name of the base class that does not extend any other classes?</p>
        <answer><code>Airplane</code></answer>
        <answer><code>Car</code></answer>
        <answer correct><code>Vehicle</code></answer>
        <answer><code>Road</code></answer>
        <explanation>The name of the base class is <code>Vehicle</code>. The other two classes extend that base Class.</explanation>
    </question>
    <question>
        <p>The <code>super()</code> command does what?</p>
        <answer correct>Calls the version of the current method found on the base class.</answer>
        <answer>Makes the current method magic.</answer>
        <answer>Copies lines of code from the base class into the current method.</answer>
        <answer>Provides a placeholder for additional development.</answer>
        <explanation>The <code>super()</code> command calls the version of the current method that exists on the base class, executing all of the code contained in the base class method.</explanation>
    </question>
    <question>
        <p>What is <code>myCar.move()</code> called in class structure terms?</p>
        <answer>a function</answer>
        <answer correct>a method</answer>
        <answer>an attribute</answer>
        <answer>a property</answer>
        <explanation>The <code>myCar.move()</code> function is called a "method" of the Car class.</explanation>
    </question>
    <question>
        <p>What is <code>myCar.numWheels</code> called in class structure terms?</p>
        <answer>a function</answer>
        <answer>a method</answer>
        <answer correct>a property</answer>
        <answer>a parameter</answer>
        <explanation><code>myCar.numWheels</code> is called a "property" of the Car class.</explanation>
    </question>
    <question>
        <p>What is <code>myCar.description</code> called in class structure terms?</p>
        <answer>a function</answer>
        <answer>a method</answer>
        <answer correct>a dynamic property</answer>
        <answer>a property</answer>
        <explanation><code>myCar.description</code> is called a "dynamic property" of the Car class because it executes a function to determine its value.</explanation>
    </question>

    <question>
        <p>What does <code>myPlane.fly('north')</code> return?</p>
        <answer correct><code>"Vehicle FLYIN1 flies north"</code></answer>
        <answer><code>"Vehicle HOTWLZ1 rolls north"</code></answer>
        <answer><code>"Vehicle FLYIN1 moves north"</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The returned value of <code>myPlane.fly('north')</code> is <code>"Vehicle FLYIN1 flies north"</code>.</explanation>
    </question>
    <question>
        <p>What is <code>myPlane.numPropellers</code> equal to?</p>
        <answer><code>4</code></answer>
        <answer correct><code>1</code></answer>
        <answer><code>2</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The value of <code>myPlane.numPropellers</code> is <code>1</code> because that is the default value and no other value was supplied when the <code>myPlane</code> instance was created.</explanation>
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
