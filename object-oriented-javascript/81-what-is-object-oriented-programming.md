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
Encapsulation is the idea that not all parts of a Class object should 

## Inheritance

## Polymorphism