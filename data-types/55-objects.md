# Objects

Just about everything in JavaScript is an Object at its base level. An Object is a Data Type (if we create an object and run `typeof()` on it, we can see that it returns `"object"`), but it is also a Data Structure. The structure of an Object allows attributes to be related. Each attribute of an Object has its own Data Type and can be used just like any standalone variable of that Data Type. Consider the following code:

```js
var foo = {}; // This is common syntax for "initializing" an empty Object.

foo.name = "Foo Object"; // In this case foo.name is a String.
foo.counter = 0; // In this case, foo.counter is a Number.
```
Looking at the code above, we can see that `foo` is initially created as an empty Object, meaning that our program would know that `foo` is an Object, but it does not yet have any custom attributes defined. In the next lines, we define two attributes of `foo`: `foo.name` and `foo.counter`. The `foo.name` attribute is a String, and the `foo.counter` attribute is a Number. These two values can be used in the same way as normal String or Number variables.

It's also useful to note the basic syntax of creating and using Objects. Curly braces (`{ }`) indicate an object, so we can use them as above to initialize an empty Object. This is a very common practice in writing JavaScript code. We can also see that assigning new attributes to an Object is just like creating new variables, except we name them using the "dot naming syntax" that is common to JavaScript. We could define as many attributes as we'd like on this Object (or any other), and we can add/change attributes at will.

Attributes can be set to any kind of Object, any Data Type, or even Functions (which are actually just Objects, too). Consider the following code:

```js
var venue = {}; // initialize the empty object `venue`
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

{% exercise %}
Define an Object called `foo`.

{% initial %}
var 

{% solution %}
var foo = {};

{% validation %}
assert(typeof(foo)==="object", "Incorrect: Your variable is not an object!");

{% endexercise %}

{% exercise %}
Define an Object called `foo` with a `name` attribute equal to "Bob".

{% initial %}
var 

{% solution %}
var foo = {};
foo.name = "Bob";

{% validation %}
assert(foo.name==="Bob", "Incorrect.");

{% endexercise %}


