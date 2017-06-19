# Working with Text

Since so much of what we do as programmers revolves around expressing logic and describing concepts or objects in text, it's crucial to build up some skills for working with text in our code. By this we mean not only working with String Data Types, but also combining Data Types to create the text we need for any given purpose.

## Concatenating Strings
Probably the most straightforward way of combining text and data is to use the concatenation operator (`+`) to cobble together strings. Here is what that looks like in code:

```js
var name = "Jane";
var destination = "library";
var distance = 1.2;

var message = "Your trip: " + name + " is going to the " + destination + " which is " + distance + "miles away.";
// `message` now contains the text: "Your trip: Jane is going to the library which is 1.2 miles away.";
```
This is a fairly easy way to understand putting text and variables together. We can combine Numbers and Strings into another string, and then we could output that `message` to the user. Note that we use the plus signs to concatenate the values together into a big string, and we must be sure to include spacing in the quotes so that we don't slam the values and text together. (Try running these lines in a JavaScript console and see what it looks like if you remove those extra spaces.)

But this method can also be difficult to manage: What if we need to put variable into a _lot_ of text? What if we need to put information from an Array into the text? What if we don't like writing so many plus signs and making sure to put spaces in our quotes correctly?

Luckily, we have more tools at our disposal.

## Joining Arrays and Splitting Strings
A common task when writing code is combining items in a list into some textual representation. Sometimes we can solve this problem using the `join()` command that comes with every Array. The [`join()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join) command allows us to specify a character that will be used between items in the list, and it outputs a string containing the generated text. Here's how it works:

```js
var fruits = ['apple', 'banana', 'orange', 'lime'];
var fruitText = fruits.join(', '); // Joins all Array items and inserts a ', ' between them.
// fruitText now contains the String: 'apple, banana, orange, lime'
```
There are many situations where using `join()` like this is a good approach. It can be even more useful when combined with the String [`split()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) command. We can use `split()` to break a String apart like so:

```js
var ogText = "Sometimes I worry about being a success in a mediocre world." // Quote is courtesy Lily Tomlin!
var textArray = ogText.split(' ');

var shoppingText = "eggs,butter,milk,bread";
var shoppingArray = shoppingText.split(',');
```


## Template Literals

{% exercise %}
Define a variable `x` equal to 10.

{% initial %}
var x =

{% solution %}
var x = 10;

{% validation %}
assert(x == 10);

{% endexercise %}

