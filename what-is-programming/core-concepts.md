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

`var myInteger = 4;`

**[Decimals](https://en.wikipedia.org/wiki/Single-precision_floating-point_format)** are numbers with decimal points. These are often required when doing calculations that might result in decimal remainders, when dealing with measurements, or in other situations where the value of a number may need to be more precise than a whole number. A decimal variable definition in JavaScript would look like this:

`var myDecimal = 3.14;`

It's very useful to note that although these numbers are called "Decimal" in JavaScript, they are often known as "Floating point" numbers or "Floats" or "Singles". You can get an overview of the more technical details about how this data type works [on the Wikipedia page](https://en.wikipedia.org/wiki/Single-precision_floating-point_format).

### Boolean

## Data Structures

### Objects

### Arrays

## Logical Flow Control 

### Conditionals

### Loops

