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
```
In this example we start, again, with a base class called `Animal`. The `Animal` class takes in a `name` parameter, but nothing else. Two more classes are created by extending the `Animal` class: `Bird` and `Dog`.



















