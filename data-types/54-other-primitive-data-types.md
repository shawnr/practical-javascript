# Other Primitive Data Types

JavaScript also gives us a few Data Types that are used in more specific ways: Boolean, Undefined, Null, and Symbols.

## Boolean

The Boolean Data Type has a value that is either `true` or `false`. These types of variables are helpful when controlling the logical flow of a program. We often use different logic to determine a `true` or `false` so that we can later have an easy check to determine the next commands the program should execute.

Boolean values are generally checked within a conditional \(an `if` statement\) or to control the execution of a `while` loop. These will be used throughout our code.

## Undefined

[Undefined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) is the type for any value that has been declared but not initialized to a value. When we write something like this, the type of the variable `foo` is `undefined`:

```js
let foo;
```

The following example indicates how this could be used in code:

```js
let foo;
if (typeof(foo) === 'undefined') {
    // Code here would execute because foo is undefined.
}
```

This is the default type for any variable that has not been assigned a value.

## Null

[Null](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) is a Data Type that is used to indicate there is nothing assigned to the variable. At first, it seems as if it's a duplicate of Undefined, but in fact it's different in an important way. We would probably never assign `undefined` as a value to a variable in our system. Remember, it is the _default_ type of a non-initialized variable.

But imagine the case where we have some variable where there _could_ be a value assigned, but at some point in our program it _does not_ have a value assigned. This is where the Null data type becomes helpful. We can set the value of a variable to `null` to indicate the variable does not currently point to a value. This is used often in API design to indicate that where there _could_ be information it is missing.

Here's an example of using `null` in code. Imagine we are writing a system trying to manage a `currentUser` object:

```js
let currentUser;
if (typeof(currentUser) === 'undefined') {
    // This code executes because foo has not been assigned a value.
}
```

Later on in our code, we might want to set the `currentUser` back to `null` to indicate no user is logged in:

```js
currentUser = null;
if (typeof(currentUser) === 'undefined') {
    // This code will not execute because currentUser is equal to null.
} else if (typeof(currentUser) === 'null') {
    // This code will execute.
    // Do something to login the user
}
```

Now, when we do the check against `'undefined'` it's `false` because `currentUser` has been defined as `'null'`.

It's common for developers to use `null` to represent missing data. Imagine an object that stores an address. We could picture that object with attributes for both "street address" and "street address line two". However, many people do not have an additional street address line to use in their addresses. In this case, the optional "street address line two" might be equal to `null` to represent that value is missing in a purposeful way.

