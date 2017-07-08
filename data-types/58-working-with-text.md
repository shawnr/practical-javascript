# Working with Text

Since so much of what we do as programmers revolves around expressing logic and describing concepts or objects in text, it's crucial to build up some skills for working with text in our code. By this we mean not only working with String Data Types, but also combining Data Types to create the text we need for any given purpose.

## Concatenating Strings
Probably the most straightforward way of combining text and data is to use the concatenation operator (`+`) to cobble together strings. Here is what that looks like in code:

```js
let name = "Jane";
let destination = "library";
let distance = 1.2;

let message = "Your trip: " + name + " is going to the " + destination + " which is " + distance + "miles away.";
// `message` now contains the text: "Your trip: Jane is going to the library which is 1.2 miles away.";
```
This is a fairly easy way to understand putting text and variables together. We can combine Numbers and Strings into another string, and then we could output that `message` to the user. Note that we use the plus signs to concatenate the values together into a big string, and we must be sure to include spacing in the quotes so that we don't slam the values and text together. (Try running these lines in a JavaScript console and see what it looks like if you remove those extra spaces.)

But this method can also be difficult to manage: What if we need to put variable into a _lot_ of text? What if we need to put information from an Array into the text? What if we don't like writing so many plus signs and making sure to put spaces in our quotes correctly?

Luckily, we have more tools at our disposal.

## Joining Arrays and Splitting Strings
A common task when writing code is combining items in a list into some textual representation. Sometimes we can solve this problem using the `join()` command that comes with every Array. The [`join()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join) command allows us to specify a character that will be used between items in the list, and it outputs a string containing the generated text. Here's how it works:

```js
let fruits = ['apple', 'banana', 'orange', 'lime'];
let fruitText = fruits.join(', '); // Joins all Array items and inserts a ', ' between them.
// fruitText now contains the String: 'apple, banana, orange, lime'
```
There are many situations where using `join()` like this is a good approach. It can be even more useful when combined with the String [`split()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) command. We can use `split()` to break a String apart like so:

```js
let ogText = "Sometimes I worry about being a success in a mediocre world." // Quote is courtesy Lily Tomlin!
let textArray = ogText.split(' ');
// textArray equals ["Sometimes", "I", "worry", "about", "being", "a", "success", "in", "a", "mediocre", "world."]

let shoppingText = "eggs,butter,milk,bread";
let shoppingArray = shoppingText.split(',');
// shoppingArray now equals ["eggs", "butter", "milk", "bread"]
```
In the example above, we can see that we have two different strings which we can split apart on characters of our choosing. We could also use the `join()` command to join them again into a string. If we use the same character to join, then we would end up with the original string:

```js
let ogText = "Sometimes I worry about being a success in a mediocre world." // Quote is courtesy Lily Tomlin!
let textArray = ogText.split(' ');

let newText = textArray.join(' ');
if (ogText === newText){
    // This code will execute because `ogText` and `newText` are identical.
    console.log('We have re-made the original text!');
}
```
Being able to break apart strings and re-combine them is helpful in many situations. For example, we often do this sort of thing when analyzing file paths or URLs. It can be helpful for allowing users to enter data in different interfaces, too, where providing a comma-separated list is more convenient than typing each item of the Array individually.

**BEWARE** Although these tools for breaking apart Strings and making them Arrays are useful, be wary of using them to replace proper Data Structures in your code or HTML interfaces.

## Template Literals
Finally, we have a great tool in JavaScript that allows us to insert data values into text in a very convenient way. [Template Literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) are defined with the backtick character (```). We can work more easily Template Literals and avoid many of the issues we previously had with String concatenation. For example, consider our concatenation example updated to use Template Literals:

```js
let name = "Jane";
let destination = "library";
let distance = 1.2;

let message = `Your trip: ${name} is going to the ${destination} which is ${distance} miles away.`;
// `message` now contains the text: "Your trip: Jane is going to the library which is 1.2 miles away.";
```
We can see that the end result is the same, but getting there is much easier on the eyes. Template Literals allow us to drop variables into Strings by referencing them with expression tags (`${expression}`). This allows us to write code that is much more simple. Template Literals can also span multiple lines, so we can do things like this:

```js
let salutation = "Dearest";
let name = "John";
let numberOfDays = 15;
let numberOfHours = 7;

let message = `${salutation} ${name},
    It's been ${numberOfHours} hours and ${numberOfDays} days
    since you took your love away.
    
    Please return it soon`;

console.log(message);
```
This code would output:

```
Dearest John,
It's been 7 hours and 15 days
since you took your love away.

Please return it soon.
```

Template Literals make it much easier to work with large chunks of text. They can span multiple lines, and their formatting stays generally intact. But they can also be made a little more dynamic by adding JavaScript expressions in addition to just inserting values from variables. Here is an example:

```js
let itemName = "Widget";
let price = 4;
let tax = 0.05;
let quantity = 3;

let receipt = `RECEIPT OF PURCHASE
    ${itemName} x ${quantity} @ ${price}
    
    Price: ${quantity * price}
    Tax: ${price * tax}
    ------------------------------------
    Total: ${price + (price * tax)}`;

console.log(receipt);
```
The code above would output the following text to the JavaScript console:

```
RECEIPT OF PURCHASE
Widget x 3 @ 4
Price: 12
Tax: 0.2
------------------------------------
Total: 4.2
```
As we can see, it's possible to do operations within the expression tags. This makes Template Literals even more flexible and useful.
    

## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Split the String `shoppingList` into an array on the commas.

{% initial %}
let textList = "bread,milk,butter,eggs";
let shoppingList = 

{% solution %}
let textList = "bread,milk,butter,eggs";
let shoppingList = textList.split(',');

{% validation %}
assert(shoppingList[0]==="bread", 'Incorrect.');

{% endexercise %}

{% exercise %}
Join the Array using a slash (`/`) as the joining character.

{% initial %}
let pathArray = ['Projects','web','resources','js','main.js'];
let filePath = 

{% solution %}
let pathArray = ['Projects','web','resources','js','main.js'];
let filePath = pathArray.join('/');

{% validation %}
assert(typeof(filePath)==="string", 'Incorrect.');

{% endexercise %}

{% exercise %}
Replace the expression tags in this template literal to insert the corresponding data.

{% initial %}
let name = "Grace Hopper";
let source = "Ships Ahoy Magazine";
let date = "July 1986";

let message = `"It's easier to ask forgiveness than it is to get permission."
    Name, Source
    Date`;

{% solution %}
let name = "Grace Hopper";
let source = "Ships Ahoy Magazine";
let date = "July 1986";

let message = `"It's easier to ask forgiveness than it is to get permission."
    ${name}, ${source}
    ${date}`;

{% validation %}
assert(message === `"It's easier to ask forgiveness than it is to get permission."
Grace Hopper, Ships Ahoy Magazine
July 1986`, 'Try again!');

{% endexercise %}

