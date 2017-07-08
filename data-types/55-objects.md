# Objects

Just about everything in JavaScript is an Object at its base level. An Object is a Data Type (if we create an object and run `typeof()` on it, we can see that it returns `"object"`), but it is also a Data Structure. The structure of an Object allows attributes to be related. Each attribute of an Object has its own Data Type and can be used just like any standalone variable of that Data Type. Consider the following code:

```js
let foo = {}; // This is common syntax for "initializing" an empty Object.

foo.name = "Foo Object"; // In this case foo.name is a String.
foo.counter = 0; // In this case, foo.counter is a Number.
```
Looking at the code above, we can see that `foo` is initially created as an empty Object, meaning that our program would know that `foo` is an Object, but it does not yet have any custom attributes defined. In the next lines, we define two attributes of `foo`: `foo.name` and `foo.counter`. The `foo.name` attribute is a String, and the `foo.counter` attribute is a Number. These two values can be used in the same way as normal String or Number variables.

It's also useful to note the basic syntax of creating and using Objects. Curly braces (`{ }`) indicate an object, so we can use them as above to initialize an empty Object. This is a very common practice in writing JavaScript code. We can also see that assigning new attributes to an Object is just like creating new variables, except we name them using the "dot naming syntax" that is common to JavaScript. We could define as many attributes as we'd like on this Object (or any other), and we can add/change attributes at will.

Attributes can be set to any kind of Object, any Data Type, or even Functions (which are actually just Objects, too). Consider the following code:

```js
let venue = {}; // initialize the empty object `venue`
venue.name = "The JS Palace";
venue.description = "The best place to work on your JavaScript code!";
venue.address = {}; // initialize another empty object called `venue.address`
venue.address.streetAddress = "123 Fake St.";
venue.address.city = "Seattle";
venue.address.state = "WA";
venue.address.zip = 98112;
```
In the code above, we can see that `venue` is an object containing information about a business location. The attributes defined on `venue` are pretty normal, but it's worth pausing to look at the `venue.address` attribute. That attribute is, itself, an Object. It is able to contain the address information in a self-contained, well-labeled block of data. 

Objects allow us to create relationships and hierarchies between information, and they are very useful for doing so. In fact, the JavaScript Object Notation (JSON) format has become so popular that it is used across virtually every other programming language to create well-defined hierarchical data structures. We will explore more about JSON in a couple sections, but first we must discuss Arrays.

## Referencing Properties of Objects
Throughout our code we will need to [reference properties of Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors). This can be accomplished in two ways: "dot-notation" and "keys". These two methods can be used interchangeably, and each is valuable for specific purposes. It's important to keep in mind these two methods of accessing the values of an Object in order to get the most from this Data Structure.

Here is some example code to review:

```js
let clubMembers = {
    grace: {
        name: "Grace Hopper",
        email: "grace@example.com"
    },
    guido: {
        name: "Guido van Rossum",
        email: "guido@example.com"
    },
    brendan: {
        name: "Brendan Eich",
        email: "brendan@example.com"
    }
}
```
In the code above, we have an Object defined that uses the usernames of club members for the primary index. This means that we could access these values in two ways:

```js
console.log(clubMembers.grace.name); // Outputs "Grace Hopper" to the console.

console.log(clubMembers['grace'].name); // Outputs "Grace Hopper" to the console.
```
The two `console.log` statements above have the same results: They print the `name` property from the object contained in the `grace` property of the `clubMembers` object. The first method of referring to the value is "dot notation" and it is often used when we know exactly which property we need to access in an Object. The second method uses a reference to a "key", which can be useful when we want to use a variable to supply that name. Consider this example:

```js
let username = "guido";

console.log(clubMembers[username].name); // Outputs "Guido van Rossum" to the console.

console.log(clubMembers['guido'].name); // Outputs "Guido van Rossum" to the console.

console.log(clubMembers.guido.name); // Outputs "Guido van Rossum" to the console.
```
In this example, you can see that the variable `username` has a value assigned to it. The value is the String, `"guido"`. This matches the "key" for the Object defined at `clubMembers.guido`. So we can access the `name` property of the Object stored at `clubMembers.guido` using either of the three syntax methods above.

The dot notation method is very clean when we know what property we need to access. But when we're using variables (such as when looping through Arrays or when correlating data from another variable or source), it's often necessary to use the "key" notation to use an expression to reference the value stored in a given property (or at a given "key").

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Define an Object called `foo`.

{% initial %}
let 

{% solution %}
let foo = {};

{% validation %}
assert(typeof(foo)==="object", "Incorrect: Your variable is not an object!");

{% endexercise %}

{% exercise %}
Define an Object called `foo` with a `name` attribute equal to "Bob".

{% initial %}
let 

{% solution %}
let foo = {};
foo.name = "Bob";

{% validation %}
assert(foo.name==="Bob", "Incorrect.");

{% endexercise %}

{% exercise %}
Set `baz` equal to the attribute `bar` in the Object `foo` without using dot notation.

{% initial %}
let key = 'bar',
let foo = {
    bar: 42
}

let baz = 

{% solution %}
let key = 'bar',
let foo = {
    bar: 42
}

let baz = foo[key];

{% validation %}
assert(baz==42, "Incorrect. Double-check your reference.");

{% endexercise %}





