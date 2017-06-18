# Other Primitive Data Types

JavaScript also gives us a few Data Types that are used in more specific ways: Undefined, Null, and Symbols.

## Undefined

[Undefined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) is the type for any value that has been declared but not initialized to a value. When we write something like this, the type of the variable `foo` is `undefined`:

```js
var foo;
```
The following example indicates how this could be used in code:

```js
var foo;
if (typeof(foo) === undefined) {
    // Code here would execute because foo is undefined.
}
```
This is the default type for any variable that has not been assigned a value.

## Null

[Null](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) is a Data Type that is used to indicate there is nothing assigned to the variable. At first, it seems as if it's a duplicate of Undefined, but in fact it's different in an important way. We would probably never assign `undefined` as a value to a variable in our system. Remember, it is the _default_ type of a non-initialized variable. 

But imagine the case where we have some variable where there _could_ be a value assigned, but at some point in our program it _does not_ have a value assigned. This is where the Null data type becomes helpful. We can set the value of a variable to `null` to indicate the variable does not currently point to a value. This is used often in API design to indicate that where there _could_ be information it is missing.

Here's an example of using `null` in code. Imagine we are writing a system trying to manage a `currentUser` object:

```js
var currentUser;
if (typeof(foo) === undefined) {
    // This code executes because foo has not been assigned a value.
}
```
Later on in our code, we might want to set the `currentUser` back to `null` to indicate no user is logged in:

```js
currentUser = null;
if (typeof(foo) === undefined) {
    // This code will not execute because currentUser is equal to null.
} else if (typeof(foo) === null) {
    // This code will execute.
    // Do something to login the user
}

```
Now, when we do the check against `undefined` it's `false` because `currentUser` has been defined as `null`. 


{% exercise %}
Define a variable `x` equal to 10.

{% initial %}
var x =

{% solution %}
var x = 10;

{% validation %}
assert(x == 10);

{% endexercise %}

