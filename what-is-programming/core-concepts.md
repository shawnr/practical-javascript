# Core Concepts in Programming

After the advent of computers, programming languages grew and proliferated. Programming languages have gone through an evolution of type and purpose, which has often coincided with the capabilities of hardware and the needs of the people using the computing devices. However, there is also an evolutionary quality to the history of programming languages. As concepts are developed they are worked through, enhanced, revised, discarded, or kept. Since there are many goals and purposes for writing software, there are many ways of doing it. 

Often, when we talk about "writing code" or "programming" we mean the act of writing instructions for the computer to follow. These instructions define different concepts and actions that the computer hardware can use to make different things happen: a pixel lights up on the screen, or a value gets written to disk. Writing the correct instructions to create our desired outcome is the challenge of coding (please note: I use the words "coding" and "programming" interchangeably since they are generally used that way in the field).

Over time, some concepts have permeated the world of programming so they exist in almost all languages. These are core concepts that make it possible to achieve different logical expressions. Using these core concepts allows us to create sets of instructions for computing hardware and to define _algorithms_ that perform specific tasks. We will review some of these core concepts below, and throughout this book we will dig more deeply into how many of these work within the JavaScript programming language. 

## Algorithms and Instructions

An **algorithm** is a "self-contained sequence of actions to be performed" ([Wikipedia](https://en.wikipedia.org/wiki/Algorithm)). Algorithms can be designed to process information, calculate a specific value, modify a digital file, or perform a sequence of actions using computer-controlled machines. This might include ingesting and annotating data received from a weather sensor, applying a filter to a photo so that it looks like it was taken by an old-time camera, calculating interest on a bank account, or controlling a mechanical arm on a factory assembly line. 

Algorithms are designed to accomplish a specific action, and a software application will often make use of several algorithms in order to deliver its full set of features. If you imagine an app like Facebook, you might recognize ways in which different algorithms are used: An algorithm governs how user authentication is handled. An algorithm modifies files that a user uploads with the app. An algorithm determines which content to show you in your news feed.

Algorithms are connected with **instructions**. Much of any software application's code is concerned with connecting discrete actions (often powered by specific _algorithms_) using sets of instructions. These instructions are what determines that, for example, when a user comes to the site they are asked to authenticate their identity. The instructions would lead the user to a page or screen where they are asked for the information they need, and then that information would be handed off to the code that comprises the _authentication algorithm_ in order to verify the user's identity. That algorithm would return a result that would then allow the app to know the user is authenticated, and other instructions would then tell the app how to behave.

It is useful to understand that as we write code we are doing different things at different times. Sometimes we are concerned with creating complex logic that performs specific tasks in an efficient manner. This practice is, often, the creation of algorithms and tends to lead to the creation of software components that can be used in many different situations.

At other times, we are writing instructions that are designed to move the user through the application, present different features to the user, and move data between all of the components of the application. This kind of coding is similar to writing algorithms, but it has different constraints and criteria for success.

In order to create either algorithms or instructions, software developers make use of a common set of concepts that exist across most programming languages. These concepts, which are built into the programming languages themselves, allow for data to be manipulated, logic to be described and enforced, and code to be interpreted by the computing hardware.

## Syntax
In all programming languages, there is a definition of **[syntax](https://en.wikipedia.org/wiki/Syntax_%28programming_languages%29)**. The syntax of a language determines the specific way lines of code must be written. Many languages require a semicolon (`;`) to end each line. Many languages use curly braces (`{` and `}`) to denote the contents of a function or loop.

Each language has a different syntax, but they all enforce their syntax, often ruthlessly. In most programming languages, a "syntax error" will break the entire application. This is often a source of frustration for new developers, but over time we get better at parsing our own code and seeing that we have missed a comma (or included an extra comma). It often seems frustrating from a human perspective to have a misplaced comma or semicolon break everything in our software (after all, in real life we can usually read past bad punctuation with little impact on our understanding). But our computing hardware has no notion of nuance or contextual interpretation (unless we've programmed it that way). It's impossible for our programming language interpreter to "figure out" what we meant, and, in the end, we don't want our interpreter to "guess" about too much. We want reliable execution of our code that is the same every time. That requires us to be as attentive to detail as the machine.

In addition to line endings and markers denoting sections of code, **[reserved words](https://en.wikipedia.org/wiki/Reserved_word)** are an important concept in a programming language's syntax. Words such as `for` or `while` are often reserved words that note specific commands within the programming language. These words are usually off-limits for making variable or function names because they are reserved for use by the programming language itself. Languages typically try to minimize the number of words they reserve in order to allow developers as much freedom of expression as possible.

Using an example from JavaScript, the reserved word `var` is used to scope a variable (don't worry too much about what that means, we will cover it later). But you could not name a variable `var` because it would conflict with the reserved word. To define a variable named `foo` that equals the number `6`, we would write:

`var foo = 6;`

The line above specifies the creation of that variable, `foo`. 

## Variables and Data Types

Within the code of a software application, different segments of code are named. This includes the names of files, functions, and **[variables](https://en.wikipedia.org/wiki/Variable_%28computer_science%29)**. Variables are the labels we give to data values within the software. We use variables to reference data values at different points in the code. 

For example, within an application there may be a variable called `user` that provides a reference to information within the software about the current user. The information contained in `user` will change depending on which person logs into the system at any given time, but within the software code that person's information will always be referenced using the variable `user`. 

Each variable references a stored value that is of a specific **[data type](https://en.wikipedia.org/wiki/Data_type)**. Data types allow the programming language to handle different kinds of values in useful ways. This is mostly designed to ease the task of writing code and increase the reliability of the resulting software. There are many data types, but below are a few of the most common.

### Text

The **[string](https://en.wikipedia.org/wiki/String_%28computer_science%29)** data type references what we typically think of as a _word_ or _text_. Strings are normally denoted with quotation marks, such as:

`var foo = "some text";`

Strings can contain a huge variety of characters (including numbers), but if they are defined as a string then they are given a set of features that are useful for working with text. In various languages, this includes functions to break strings apart (such as separating all the words following spaces), to combine strings together, or to change/replace various characters within the string. 

### Numbers

There are two major data types used for working with numbers: **[Integers](https://en.wikipedia.org/wiki/Integer_%28computer_science%29)** are whole numbers such as `1`, `42`, or `1337`. These are often used as counters or index numbers. This is what it looks like in JavaScript to define an integer:

`let myInteger = 4;`

**[Floating point numbers](https://en.wikipedia.org/wiki/Single-precision_floating-point_format)** are numbers with decimal points. These are often required when doing calculations that might result in decimal remainders, when dealing with measurements, or in other situations where the value of a number may need to be more precise than a whole number. A decimal variable definition in JavaScript would look like this:

`let myDecimal = 3.14;`

It's very useful to note that, as of recent versions of the ECMAScript standard, JavaScript has only one type for [Numbers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type).

### Boolean

Within software development, we often talk about the "binary" nature of computer hardware. All computer hardware is, ultimately, comprised of very tiny switches. Billions of switches are etched onto a chip, and all of our programming logic is reduced to an "on" or "off" signal for each switch. Turning these switches on and off allows different actions to be executed by the hardware.

In Mathematics, [Boolean Algebra](https://en.wikipedia.org/wiki/Boolean_algebra) is the practice of using logical deduction to determine _true_ and _false_ values within a system. We often do this kind of work in our code, and in order to support these calculations, we have the **[Boolean](https://en.wikipedia.org/wiki/Boolean_data_type)** data type.

For example, in a software application like Facebook, it's crucial to know whether the user is logged in or not. This might involve making several checks, and with each check a boolean value might be recorded. In JavaScript, that could look something like this:

`user.loggedIn = true;`

The two values for a boolean data type within JavaScript are `true` and `false`. We use boolean variables to control logical flow throughout applications in most programming languages.

## Data Structures

In addition to variables, software developers make use of **[data structures](https://en.wikipedia.org/wiki/Data_structure)**. Data structures are ways of containing data that make it more convenient for the developer to work with that data. Data structures often make it more efficient for the computing hardware to handle the data being processed, so using the correct data structure for the task is a key factor in writing performant applications.

Within JavaScript there are two data structures that are similar to structures in many other programming languages: objects and arrays.

### Arrays

**Arrays** are sometimes known as "lists" or "indexed arrays" in other programming languages. An Array contains an _indexed_ list of items. The items can be of any data type, and they can be referenced using their numerical index. For example, here is an Array assignment in JavaScript:

`let myArray = ['hello', 'world', 42];`

The example Array above has three items and they can be accessed using their numerical index. The value of `myArray[2]` is `42`. The value of `myArray[0]` is `'hello'`.

Arrays are very useful for storing lists of values.

### Objects

**[Objects](https://www.w3.org/wiki/Objects_in_JavaScript)** are foundational in JavaScript, and they are very common in other languages. In other programming languages they are sometimes known as "hashes" or "dictionaries" due to the way they work. 

An object is defined with specific _attributes_. These attributes are accessed by name. The [JavaScript Object Notation](http://www.json.org/) (JSON) is used across many platforms and languages because of its clean, simple syntax. Here is what a JavaScript Object definition looks like:

```js
let myObject = {
    name: 'Grace Hopper',
    rank: 'Rear Admiral',
    favoriteTech: ['COBOL', 'compilers']
};
```

In order to access the values within the Object, we would reference the attributes by name: `myObject.name` equals `'Grace Hopper'`. `myObject.rank` equals `'Rear Admiral'`. It's interesting to note that the value of `myObject.favoriteTech` is an array. Object attributes may contain Arrays. Likewise, Arrays may contain items that are Objects.

## Controlling Logical Flow 

In order to define the instructions and algorithms of an application, it's important to control the way code executes--the "flow" of the program. We organize code into different sections so that we can make good use of the different pieces of logic we have created. As a user interacts with our software, it's important to move through the code in ways to support our desired outcomes.

For example, if the user wishes to login, we must move the user to the login page/screen and then execute the login process for the user: take in their login credentials, process that, and provide a response based on our analysis of the information they have supplied. 

In order to make this happen we primarily use three different kinds of structures: functions, conditionals, and loops.

### Functions

Most programming languages allow you to define **[functions](https://en.wikipedia.org/wiki/Subroutine)** (sometimes called "subroutines"). These are contained lines of code that are typically dedicated to just one purpose. Functions are an abstraction that is typically used to encapsulate some specific logic that can be called from multiple places within the software code. 

For example, let's assume we are writing an application in JavaScript that requires us to take mixed-case strings and make them entirely uppercase. We can define a function like this:

```js
function makeUppercase(text){
    return text.toUppercase();
}
```

The function defined above is called `makeUppercase` and it expects to receive a value that it labels `text`. The function then returns the results of the `text.toUppercase()` function, which is a built-in function for strings in JavaScript (and part of the value of having data types). 

To use this function we might write:

```js
let mixedText = "Hello, world!";
let uppercaseText = makeUppercase(mixedText);
console.log(uppercaseText); // Would print "HELLO, WORLD!" in the console.
```

This is a mundane example, but functions are used extensively in most types of programming languages and software projects. 

### Conditionals

As we read above, Boolean data types are useful for managing logical flow. We use conditionals to evaluate Boolean and other variables and then execute code accordingly. In most languages conditionals are structured as `IF`, `THEN`, `ELSE` statements. These statements cause the programming language interpreter to evaluate our statements and then determine which statement is `true`. The statement that is `true` is the one that gets executed. 

Here is an example (again, in JavaScript) from an imaginary web application:

```js
if (!user.logged_in){
    // User is not yet logged in
    // Redirect to login page
    app.location.go('/login');
} else if (user.role === 'staff') {
    // User is logged in and their role is staff
    // Redirect to admin homepage
    app.location.go('/admin');
} else {
    // User is logged in, but is not staff
    // Redirect to user homepage
    app.location.go('/home')
}
```

Conditional statements are able to be strung together. In the example above, we can see that the conditional check would progress from top to bottom, and the first condition that results in a `true` value would be executed. The first check determines whether the user is logged in, and if they are **not** logged in then it will redirect them to a login page. If the user **is** logged in, then it would check the user's role. If the role is `'staff'`, then the user is redirected to the admin dashboard. However, if the user is not a staff member, then they are redirected to their user homepage.

This is just an imaginary example, but it's close to what we actually do in web apps to manage where users should go when they arrive on the site. Much of our efforts as software developers are put towards setting up the ability to write these conditionals so that we can determine what our app should do next. Conditionals are used to determine almost every decision our applications make.

### Loops

We have reviewed the data structures Object and Array, which are used to store and relate complex information. When working with these structures, or just when executing functions in general, it's often useful to be able to **loop** through tasks. For example, if I have a large Array containing information about every book about a topic, then I might want to loop through those books and display information about each one for the user.

In most languages we have two kinds of loops: **[for](https://en.wikipedia.org/wiki/For_loop)** and **[while](https://en.wikipedia.org/wiki/While_loop)**. The `for` loop is used to cycle through all of the data stored in a data structure (usually an Array). They are often used to output the results of some data.

Example `for` loop:

```js
for (i=0; i<=myArray.length; i++){
    // Do something with data
    console.log(myArray[i]);
}
```

The `for` loop above goes through the Array `myArray` and outputs the value of each item to the console. The syntax for this loop varies depending on language, and many languages have adopted an easier `foreach` loop syntax that essentially performs the same function.

The `while` loop executes as long as some condition is true. An example would look like:

```js
var counter = 0;
while(counter < 100){
    // this code will execute until the value of counter is 100
    counter = counter + 1;
}
```

In the example above, the `while` loop continues until the counter reaches a certain number. In other cases, a `while` loop may be watching for another value to change within the system, such as when a process has finished and data can be updated. In general, `while` loops are used less often and are seen as being a little more risky because it's possible to create situations where the `while` loop might run forever (which breaks our applications).

## How Code is Interpreted

All code is interpreted by some kind of system. That system reads through the code following specific rules and interpreting each line. Some common coding structures define code that does not run until it needs to be invoked. Other lines of code are executed at the moment they are read. 

A common concept in a code interpreter is a "pointer". A pointer is the indication of where in the code the interpreter is reading at any given moment. The pointer indicates what line and character the interpreter is reading, and when the interpreter encounters an error it can report the position of the pointer to help us hone in on where the error might have happened.

Visualizing the pointer moving through code can be a good way to better understand what's happening when you "run" a program. Here is a video illustration that demonstrates how the pointer moves through some example code.

{% youtube %}https://www.youtube.com/watch?v=mMQ9XfKASKc{% endyoutube %}

## Conclusion

This is just a brief, general overview of some core concepts that tend to exist across programming languages. The rest of this book will go much deeper into the ways these concepts are expressed in JavaScript. 
