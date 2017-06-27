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
```
Often a `constructor()` function is designed to accept parameters that define the specific instance of the Class object.