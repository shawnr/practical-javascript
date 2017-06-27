# What is Object Oriented Programming?

At this point it should be clear that when we are programming we are primarily concerned with two things: 

1. Representing what we know about the world (data) in a way that can be understood and manipulated to meet our needs.
2. Representing actions we can perform on data in a way that can be understood and used effectively.

In order for this to work, we must make many conceptual leaps: We need to figure out how to describe facts about the world in text. We must be able to represent measurements and the complexity of relationships using symbolic expressions. We want to create logical connections between parts of our programs that are both functional for the computing environment and understandable by human beings.

Because of these and many other requirements of writing software, we have developed the notion of Object Oriented Programming (OOP) to effectively describe and execute both data and functionality. OOP allows us to define "Classes" of objects that possess both "properties" and "methods". Object Classes allow us to describe objects and concepts in great detail; we can think of them as the "nouns" of OOP. Properties can be thought of as "adjectives"; they describe the details of the Class. The methods are the "verbs" of OOP; they _do_ things, executing functionality, manipulating data, or providing some kind of input/output.

An example of a Class in JavaScript might look like this:

```js
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
  calcArea() {
    return this.height * this.width;
  }
} 
```
In the example above, a Class is created called `Rectangle`. This Class has two properties: `height` and `width`. Those properties _describe_ the rectangle. It also has a method called `calcArea()` that can be invoked in order to return the area of the rectangle. This method allows the Class to _do_ something. This Class models the concept of a rectangle in a fairly thorough way. We could use it to represent rectangles in our code as much as we needed. 

Of course the basic structure of the Class is just the beginning of how OOP works. OOP is ruled by four fundamental concepts that help us understand how to use Classes most effectively.

## Abstraction
Abstraction is the idea that we want to use our Class objects to take away complexity as much as possible. Abstraction is part of our daily lives. We know how to drive a car: turn it on, put it in gear, press the gas or the brake as needed. We do not need to understand precisely how each of these actions is performed by the electromechanical systems of the car. We only need to understand the interface for the car. Once we learn the interface, we can make effective use of the car without learning how to build a car from scratch.

The notion of defining and using an interface for code we have written ourselves is actually one we've already gotten used to. We use abstraction anytime we organize code into functions or subroutines: We wrap up more complex logic and instructions into a simple command we can issue wherever we need it. Imagine the example below:

```js
function calculateTax(subtotal){
  // Perform whatever complex logic needs to happen to determine `localTaxRate`
  let localTaxRate = 0.065;
  return subtotal * (1 + localTaxRate);
}

let total = calculateTax(subtotal);
```
In this example we can see that a function called `calculateTax()`has been created to handle the calculation of the tax. There could be any number of instructions or lines of logic used to determine the applicable tax rate, but we don't have to think about all of that code when we use the function to figure out the total cost of a transaction. We have "abstracted" the logic used to calculate the tax rate, and the only thing we need to remember as developers is to call the function and supply the subtotal.

We often define Class objects that have very complex code inside them. They might perform communication with remote systems, calculations beyond our limited Math skills, or other functions that require precision and many steps. By abstracting the complexity of these features way to simple interfaces we are able to define conceptual tools in our code that are easy and intuitive to use.

## Encapsulation
Encapsulation is the idea that not all parts of a Class object should be available for public manipulation. By "hiding" or making certain data or functions unavailable outside of the Class object, we can make sure that those components are not altered by some unforeseen outside force. We do not want to accidentally change a value or execute a function that might cause our entire system to throw an error. Where possible, it is better to allow as few publicly available properties and methods as possible because it presents a cleaner interface to the Class object.

Encapsulation is supported in JavaScript through the `prototype` mechanism, but it is not easily achieved with strong enforcement and low effort. Instead, most developers have adopted the convention of prefixing any "private" property or method of a Class object with an underscore (`_`). This at least conveys to developers which properties and methods are not intended for direct use. When we encounter properties or methods named with an underscore, it's best to avoid using them directly. Thre should be a "public" property or method that provides an equivalent result. 

## Inheritance
Class objects are often hierarchical. This matches the way we have organized and categorized objects in the real world. For example, we can organize living things into "Plants" and "Animals", the Kingdoms of biological taxonomy. Within each of these Kingdoms are many sub-groupings of life forms that traverse organizational hierarchies like Phylum, Family, Genus, and Species. It is not unusual for Class objects in a system to incorporate a similar hierarchy.

For example, imagine a general Class object for `Animal`:

```js
class Animal {
  constructor(name){
    this.name = name;
  }
}
```
The base class for `Animal` has only one property: `name`. If we wish to make a class to represent a `Dog` then we could inherit from the `Animal` class and extend its functionality:

```js
class Animal {
    constructor(name){
        this.name = name;
    }
}
class Dog extends Animal {
    speak(){
        console.log(`${this.name} says, 'Woof!'`);
    }
}
let d = new Dog('Fido');
d.speak() // Outputs `Fido says, 'Woof!'` to the JS console.
```
In this example, we can see that the class `Dog` has been created by _extending_ the class `Animal`. The `Dog` class does not need to re-declare the `constructor()` method because it has _inherited_ this method. But the `Dog` class can _add_ to the definition of the class. In this case, the `Dog` class extends the `Animal` class by adding a `speak()` method.

## Polymorphism
Although building on the foundations of other Class objects in a hierarchical way is a powerful tool for modeling complex relationships and/or objects, we require one more ability in order to truly make efficient use of the Class objects we have defined. Polymorphism is the ability to _change_ the things that have been inherited from one class to another. Here is an example:

```js
class Animal {
  constructor(name){
    this.name = name;
  }
  speak(){
    console.log(`${this.name} makes a sound.`);
  }
}
let a = new Animal('Corvo');
a.speak(); // Outputs `Corvo makes a sound.` to the JS console.

class Cat extends Animal {
  speak(){
    console.log(`${this.name} meows.`);
  }
}
let k = new Cat('Fluffy');
k.speak(); // Outputs `Fluffy meows.` to the JS console.
```
In the example code above, the `Cat` class extends the `Animal` class. This time, the `Animal` class provides a `speak()` method, but it is very generic ("makes a sound"). The `Cat` class extends `Animal` and overrides the `speak()` method to provide a more cat-like response. This is polymorphism at work: the same method used with these two related Class objects will produce a different result. 

It's important to notice that in spite of the complexity of the hierarchical relationships and the "mutation" or "change" of the `speak()` method, the interface of the `Animal` and `Cat` classes remains consistent and understandable for the developer. As long as a developer knows that they can instantiate an instance of either class and then call the `speak()` method they can make use of these Class objects. Changing what the `Cat` says does not require the developer to learn a new process or method.

We will investigate more of how Class objects are created and used in JavaScript on the following pages.

**Note:** Animal examples on this page were drawn largely from the Mozilla Developers Network page, ["Classes"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes).
