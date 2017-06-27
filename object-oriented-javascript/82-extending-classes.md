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

