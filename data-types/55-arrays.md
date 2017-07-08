# Arrays

Objects work a lot like dictionaries: If you know what you want to look up, then it's very easy to get information. But there are many times when we don't need a full dictionary, we only need a list of items. Consider the case where we want to keep track of a list of items to purchase at the grocery? Or a list of people in a group? Or a list of tags that have been applied to content in our system?

In these cases, it's better to use a Data Structure like an [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). Arrays are _indexed_ collections of information. This means that each item in the Array can be referenced by a number that indicates its position in the Array.

Here is some code that demonstrates creating and accessing information in an Array:

```js
let sandwich = ['lettuce', 'mayo', 'turkey']; // A list called `sandwich` has been created with three items in it.
```
In the example above, a list called `sandwich` has been created with three items in it: 'lettuce', 'mayo', and 'turkey'. Each of these items is a String, but Arrays can contain any data types:

 ```js
 let sampleObject = {};
 sampleObject.name = "Demo";
 let crazyList = ['Zimbabwe', 42, sampleObject, false];
 ```
In this second example, `crazyList` contains items of differing Data Types. The first is a String, then a Number, then an Object, and then a Boolean. Arrays are flexible and useful for holding sets of things that need to go together.

Arrays also come with some features that make it easy to work with them. One of the most useful is the `length` attribute. We can determine how many items are in an array by using this attribute like so:

```js
let flowers = ['rose', 'carnation', 'daffodil'];
console.log(flowers.length) // Will output `3` to the console.
```
Accessing the length attribute on an Array is especially useful when presenting information about data to users (e.g. How many tags on this content item?, etc.) or when you're looping through Arrays using other methods (which we will discuss in the next section).

## Accessing Items in an Array
JavaScript Arrays are "zero indexed" which means that they begin counting their items with the number `0`. To access any item in an Array, we can reference the position of the item using the number that corresponds to that item's position. Here is an example:

```js
let dogs = ['retriever', 'hound', 'mutt'];
console.log(dogs[0]); // Prints 'retriever' to the console.
console.log(dogs[1]); // Prints 'hound' to the console.
console.log(dogs[2]); // Prints 'mutt' to the console.
```
As we can see in this example, a list with three items will fill positions `0`, `1`, and `2` in the Array. To access any of these positions, we can use the square bracket notation to reference a specific index within the Array: `dogs[1]` to reference `'hound'`, for example.

It's also possible and common to loop over items in an Array, and there are some built-in tools that make it very convenient to do that in our code. We will dig deeper into that in the next section when we talk about loops more generally.

## Adding Items to an Array

A list is much more useful when you can add new items to it. To accomplish this, Arrays have a `push()` command that can add an item to the end of the list:

```js
let tags = ['js', 'programming', 'educational']; // An Array called `tags` is created with three items.
tags.push('book'); // The item `book` has been added to the Array.
```
By using the `push()` command, we have added the String `book` to the Array called `tags`. That Array now looks like this in our code: `['js', 'programming', 'educational', 'book']`. We could continue adding new items as needed.

## Removing Items from an Array

There are three ways to remove items from an Array: `shift`, `pop`, and `splice`. Each of these provides a very specific way to remove items from the Array.

To remove the item at the beginning of the Array, use the `shift()` command:

```js
let fruits = ['apple', 'orange', 'banana']; 
fruits.shift(); // Removes 'apple' from the list leaving ['orange', 'banana'].
// `fruits` is now equal to ['orange', 'banana']
```

To remove the item at the end of the Array, use the `pop()` command:

```js
let fruits = ['apple', 'orange', 'banana']; 
fruits.pop(); // Removes 'banana' from the list leaving ['apple', 'orange'].
// `fruits` is now equal to ['apple', 'orange']
```

The two previous commands are simple and straightforward. The next way to remove items from an Array is a little more complex. 

To remove one or more items from within an Array, use the `splice()` command. The `splice()` command takes two parameters: The position to begin removing, and how many items to remove after that position. Of course, in order to get the most from this command we often need to first use another command, `indexOf()`. We can use `indexOf()` to find the position of an item in an Array. Here is an example of using both of these tools to remove several items from an Array:

```js
let colors = ['blue', 'red', 'green', 'yellow', 'black', 'white'];
let position = colors.indexOf('yellow'); // The `position` variable will be set to `3` since that is the index for the item 'yellow' in this Array.
colors.splice(position, 2); // This command removes 'yellow' plus the one item following 'yellow' (which is 'black').
// `colors` is now equal to ['blue', 'red', 'green', 'white']
```
In this example we can see that the `colors` array consists of six items. We use `indexOf('yellow')` to determine the position of `'yellow'` in the Array. Then, we use that position value with the `splice(position, 2)` command to remove `'yellow'` and the item following it (which is `'black'`). The `2` in our `splice()` command indicates that two items should be removed from the Array.

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Define an Array called `names` with a length of 4.

{% initial %}
let names =

{% solution %}
let names = ['Ada', 'Katherine', 'Grace', 'Donna'];

{% validation %}
assert(names.length===4, 'Incorrect: Your Array is not the correct length.');

{% endexercise %}

{% exercise %}
Remove the first item from this Array.

{% initial %}
let vehicles = ['truck', 'bus', 'ship', 'airplane', 'rocket'];

{% solution %}
let vehicles = ['truck', 'bus', 'ship', 'airplane', 'rocket'];
vehicles.shift();

{% validation %}
assert(vehicles[0]==='bus', 'Incorrect: You removed the wrong item.');

{% endexercise %}

{% exercise %}
Remove the last item from this Array.

{% initial %}
let vehicles = ['truck', 'bus', 'ship', 'airplane', 'rocket'];

{% solution %}
let vehicles = ['truck', 'bus', 'ship', 'airplane', 'rocket'];
vehicles.pop();

{% validation %}
assert(vehicles[vehicles.length-1]==='airplane', 'Incorrect: You removed the wrong item.');

{% endexercise %}


{% exercise %}
Remove the the items 'bus' and 'ship' from this Array.

{% initial %}
let vehicles = ['truck', 'bus', 'ship', 'airplane', 'rocket'];

{% solution %}
let vehicles = ['truck', 'bus', 'ship', 'airplane', 'rocket'];
let position = vehicles.indexOf('bus');
vehicles.splice(position, 2);

{% validation %}
assert(vehicles[1]==='airplane', 'Incorrect: You removed the wrong items.');

{% endexercise %}






