# Extending Classes
When working with Class objects in our code, it's often useful to inherit and extend their functionality. This allows us to add custom functionality without recreating the entire structure of the Class. We can often use complex Class structures provided by third-party modules and libraries by extending their Class objects and adding the features we need.

As mentioned before, Class objects lend themselves to a hierarchical relationship. They can build complex and unique behavior by pulling together a whole chain of inheritance. Here is an example of a simple Class inheritance:

```js
class Animal {
    constructor(name){
        this.name;
    }
    speak(){
        console.log(`${this.name} made a noise.`);
    }
}

class Bird extends Animal {
    speak(){
        console.log(`${this.name} chirps.`);
    }
    fly(){
        console.log(`${this.name} takes to the air!`);
    }
}
```
In this example, we have a base class for `Animal` that has been defined. The `Animal` class takes a `name` as a parameter to initialize an instance of the class. It also provides a `speak()` method that is generic to any animal. The `Bird` class _extends_ the `Animal` class (using the `extends` command) and overrides the `speak()` method to provide a more bird-like voice. The `Bird` class _also_ adds a `fly()` method, since birds can fly. 

## `super()`
In some cases, we want to keep everything about a method the same, but then add a little extra functionality to it. Take the following example into consideration:

```js
class Animal {
    constructor(name){
        this.name;
    }
    speak(){
        console.log(`${this.name} made a noise.`);
    }
    move(){
        console.log(`${this.name} begins to move.`);
    }
}

class Bird extends Animal {
    constructor(name, color){
        super(name);
        this.color = color;
        this.numLegs = 2;
    }
    speak(){
        console.log(`${this.name} chirps.`);
    }
    move(){
        super();
        console.log(`${this.name} takes flight!`);
    }
}
class Dog extends Animal {
    constructor(name){
        super(name);
        this.numLegs = 4;
    }
    speak(){
        console.log(`${this.name} barks.`);
    }
    move(){
        super();
        console.log(`${this.name} walks.`);
    }
}
let tweetie = new Bird('Tweetie Pie', 'yellow');
tweetie.speak(); // Outputs `Tweetie Pie chirps.` to the JS console.
tweetie.move(); // Outputs `Tweetie Pie begins to move.` and `Tweetie Pie takes flight!` to the JS console.

let rolf = new Dog('Rolf');
rolf.speak(); // Outputs `Rolf barks.` to the JS console.
rolf.move(); // Outputs `Rolf begins to move.` and `Rolf walks.` to the JS console.
```

In this example we start, again, with a base class called `Animal`. The `Animal` class takes in a `name` parameter, but nothing else. Two more classes are created by extending the `Animal` class: `Bird` and `Dog`. Each of these classes uses `super()` to preserve some of the functionality of specific methods. Each one uses `super()` in the `constructor()` method to preserve the assignment of the `name` property on the Class. They also use the `super()` command in the `move()` method, which preserves the first line of the JS console output.

Using the ability to extend and alter existing Classes, we can accomplish a lot without having to rewrite code or re-design our data and code structures from scratch. Many third-party modules use these concepts to provide powerful tools that, like the cars we drive every day, can be effectively used without being fully understood. This empowers us as developers to accomplish more and to stand on the shoulders of developers who have come before us.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.

{% exercise %}
Extend the `User` class to create an Admin user that uses the `super()` command to add a property called `is_staff` and a method called `checkPermissions()` that will check to verify that `is_staff` equals `true` and will return `true` or `false` accordingly.

{% initial %}
// User Class
class User {
    constructor(name, email){
        this.name = name;
        this.email = email;
    }
}
// Write Admin Class here.

// Do not change these lines.
let admin1 = new Admin('Jane Doe', 'jane@example.com');
let verified = admin1.checkPermissions();

{% solution %}
// User Class
class User {
    constructor(name, email){
        this.name = name;
        this.email = email;
    }
}
// Write Admin Class here.
class Admin extends User {
    constructor(name, email){
        super(name, email);
        this.is_staff = true;
    }
    checkPermissions(){
        return this.is_staff;
    }
}
// Do not change these lines.
let admin1 = new Admin('Jane Doe', 'jane@example.com');
let verified = admin1.checkPermissions();

{% validation %}
assert((admin1.name=='Jane Doe' && verified==true), "Incorrect.");

{% endexercise %}























