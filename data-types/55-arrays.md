# Arrays

Objects work a lot like dictionaries: If you know what you want to look up, then it's very easy to get information. But there are many times when we don't need a full dictionary, we only need a list of items. Consider the case where we want to keep track of a list of items to purchase at the grocery? Or a list of people in a group? Or a list of tags that have been applied to content in our system?

In these cases, it's better to use a Data Structure like an [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). Arrays are _indexed_ collections of information. This means that each item in the Array can be referenced by a number that indicates its position in the Array.

Here is some code that demonstrates creating and accessing information in an Array:

```js
var sandwich = ['lettuce', 'mayo', 'turkey']; // A list called `sandwich` has been created with three items in it.
```
In the example above, a list called `sandwich` has been created with three items in it: 'lettuce', 'mayo', and 'turkey'. Each of these items is a String, but Arrays can contain any data types:

 ```js
 var sampleObject = {};
 sampleObject.name = "Demo";
 var crazyList = ['Zimbabwe', 42, sampleObject, false];
 ```
In this second example, `crazyList` contains items of differing Data Types. The first is a String, then a Number, then an Object, and then a Boolean. Arrays are flexible and useful for holding sets of things that need to go together.

## Adding Items to an Array

A list is much more useful when you can add new items to it. To accomplish this, Arrays have a `push()` command that can add an item to the end of the list:

```js
var tags = ['js', 'programming', 'educational']; // An Array called `tags` is created with three items.
tags.push('book'); // The item `book` has been added to the Array.
```
By using the `push()` command, we have added the String `book` to the Array called `tags`. That Array now looks like this in our code: `['js', 'programming', 'educational', 'book']`. We could continue adding new items as needed.

## Removing Items from an Array

There are three ways to remove items from an Array: `shift`, `pop`, and `splice`. Each of these provides a very specific way to remove items from the Array.

To remove the item at the beginning of the Array, use the `shift()` command:

```js
var fruits = ['apple', 'orange', 'banana']; 
fruits.shift(); // Removes 'apple' from the list leaving ['orange', 'banana'].
```

To remove the item at the end of the Array, use the `pop()` command:

```js
var fruits = ['apple', 'orange', 'banana']; 
fruits.pop(); // Removes 'banana' from the list leaving ['apple', 'orange'].
```

The two previous commands are simple and straightforward. The next way to remove items from an Array is a little more complex. 

To remove one or more items from within an Array, use the `splice()` command. The `splice()` command takes two parameters: The position to begin removing, and how many items to remove after that position.


{% exercise %}
Define a variable `x` equal to 10.

{% initial %}
var x =

{% solution %}
var x = 10;

{% validation %}
assert(x == 10);

{% endexercise %}

