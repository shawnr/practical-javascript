# Creating and Using Classes

In JavaScript we use the `class` command to define a new Class object. This command is followed by a specific structure that looks like this:

```js
class ClassName {
    constructor([parameters]){
    
    }
    methodName([parameters]){
    
    }
}
```
The ECMAScript 6 syntax makes defining a Class object straightforward: We use the `class` command, then provide a name. By convention, class names should be "CapitalizedCamelCase" (first letter capitalized, and capitalize the first letter of each word in the name with no spaces).

Once the class has been created, it needs a `constructor` function. This method is invoked when a new instance of the class is created, and it sets up the class for working with later. Here is an example:

```js
class Car {
    constructor(make, model, year, vin, mileage){
        this.make = make;
        this.model = model;
        this.year = year;
        this.vin = vin;
        this.mileage = mileage;
    }
}
let myCar = new Car('AMC', 'Pacer', '1981', 123456, 10000);
console.log(myCar.make); // Outputs 'AMC' to the JS console.
console.log(myCar.model); // Outputs 'Pacer' to the JS console.
```
Often a `constructor()` function is designed to accept parameters that define the specific instance of the Class object. In the case of the example code, we have created a `Car` class that accepts a range of parameters to describe a car. Then we create an instance of the `Car` class called `myCar`. The `myCar` object contains all the properties and methods of the `Car` class, but it has been populated with specific data because the `constructor()` function has been called.

Of course, what good is a car if we can't drive it? 

## Methods

In order to _do_ things with our Class objects, we must create methods. Methods are functions that live within the object structure of the Class. They can perform actions on our data or within our code to fulfill the user's needs. We can enhance the `Car` example with some methods:

```js
class Car {
    constructor(make, model, year, vin, mileage){
        this.make = make;
        this.model = model;
        this.year = year;
        this.vin = vin;
        this.mileage = mileage;
    }
    drive(miles){
        this.mileage = this.mileage + miles;
        console.log(`Vroom! We drove ${miles} miles.`);
    }
}
let myCar = new Car('AMC', 'Pacer', '1981', 123456, 10000);
myCar.drive(250); // Outputs `Vroom! We drove 250 miles.` to the JS console.
console.log(myCar.mileage); // Outputs '10250' to the JS console.
```
In this example the `Car` class has gained a `drive()` method. The `drive()` method takes in a parameter called `miles`, which it adds to the total mileage when it's called. So now we have a `Car` object called `myCar` that can drive some number of miles. The `drive()` method also adds the miles driven to our total mileage. As a developer, we do not need to make a separate call to keep a tally of the number of miles we've driven or use any extra code. This is a good example of "abstraction" in our Class definition that keeps the interface to our Class object simple.

## Dynamic Properties

With properties and methods we can do a lot with our Class objects. However, we sometimes need to calculate properties of an object based on the values of some other properties. And sometimes calculating those values needs to happen each time the property is accessed. Consider the example of our car above. What if we wanted a quick and easy way to get a description that told us the information about our Car object? We would want to include mileage, but that is a property that will change each time we `drive()` the car, so we cannot just calculate this description once and be done (otherwise we could just do the calculation in the `constructor()` method).

Using our Class and data from above, we want to output something like "1981 AMC Pacer with 10000 miles" as a description. We _could_ define a method that would `return` that string, but then we'd have to "call" the method, which would be a little out of sync for a "property" like `description`. Instead, what we really want is to define a "dynamic property" that we can reference normally. To do that, we will use the `get` command:

```js
class Car {
    constructor(make, model, year, vin, mileage){
        this.make = make;
        this.model = model;
        this.year = year;
        this.vin = vin;
        this.mileage = mileage;
    }
    get description() {
        return `${this.year} ${this.make} ${this.model} with ${this.mileage} miles`;
    }
    drive(miles){
        this.mileage = this.mileage + miles;
        console.log(`Vroom! We drove ${miles} miles.`);
    }
}
let myCar = new Car('AMC', 'Pacer', '1981', 123456, 10000);
myCar.drive(250); // Outputs `Vroom! We drove 250 miles.` to the JS console.
console.log(myCar.description); // Outputs "1981 AMC Pacer with 10250 miles" to the JS console.
myCar.drive(250); // Outputs `Vroom! We drove 250 miles.` to the JS console.
console.log(myCar.description); // Outputs "1981 AMC Pacer with 10500 miles" to the JS console.
```
The `get` command allows for accessing the `description()` method as if it is a property. The method is called each time we access `Car.description` like a normal property. We now have a dynamic property that updates every time it is called. The more we `drive()`, the more that is reflected in the `description`.

Now that we can create well-featured Class objects, we can move on to exploring how leverage the concept of inheritance. 

<div class="tip-box">

<h3>What is <code>this</code>?</h3>

<p>The keyword <code>this</code> in JavaScript can be tricky to track in all contexts. It usually refers to the current code block (Function, Class, etc.). In the case of a Class object definition, the <code>this</code> keyword refers to the Class itself. That's why we refer to <code>this.property</code> inside methods when accessing Class properties. (<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this">See this article for more about <code>this</code></a>)</p>

</div>


## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.



{% exercise %}
Define a Class called `Book` with `title` and `author` properties that can be set by the developer when instantiating the Class. 

{% initial %}
// Write Book Class here.

// Do not change this line.
let book1 = new Book('Slaughterhouse Five', 'Kurt Vonnegut Jr.');

{% solution %}
class Book {
    constructor(title, author){
        this.title = title;
        this.author = author;
    }
}
let book1 = new Book('Slaughterhouse Five', 'Kurt Vonnegut Jr.');

{% validation %}
assert((book1.title=='Slaughterhouse Five' && book1.author=='Kurt Vonnegut Jr.'), "Incorrect.");

{% endexercise %}


{% exercise %}
Define a Class called `Book` with `title`, `author`, `numReviews`, and `totalScore` properties. Create a method called `review` that accepts a number representing a review score. The `review` method must increment the `numReviews` property and add the review score to the `totalScore` property. Also, add a dynamic property called `rating` that calculates the average of the reviews (`totalScore` divided by `numReviews`).

{% initial %}
// Write Book Class here.

// Do not change this line.
let book1 = new Book('Slaughterhouse Five', 'Kurt Vonnegut Jr.');
book1.review(4);
book1.review(2);
console.log(book1.rating);

{% solution %}
class Book {
    constructor(title, author){
        this.title = title;
        this.author = author;
        this.numReviews = 0;
        this.totalScore = 0;
    }
    get rating(){
        return this.totalScore / this.numReviews;
    }
    review(score){
        this.numReviews++;
        this.totalScore = this.totalScore + score;
    }
}
let book1 = new Book('Slaughterhouse Five', 'Kurt Vonnegut Jr.');
book1.review(4);
book1.review(2);
console.log(book1.rating);

{% validation %}
assert((book1.title=='Slaughterhouse Five' && book1.rating==3), "Incorrect.");

{% endexercise %}








