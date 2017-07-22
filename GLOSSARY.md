## anonymous function
A function that is defined as part of a method call or object definition such that it does not take on a name of it's own. Here is an example of an anonymous function used in an `addEventListener()` method call.

```js
let button = document.querySelector('button');
button.addEventListener('click', function(event){
    console.log('Click event was triggered.');
});
```

## compiled language
A description of a programming language that uses a "compiler" to create an executable file.

## compiler
An application used to convert source code in a given programming language into an executable file that can be run by computing hardware. (See also: compiled.)

## default actions
An action executed in the browser in response to a page event (e.g. click, submit, load, etc.).

## dynamic language
A description of a programming language that infers or determines the datatypes of variables without requiring explicit declaration.

## Ecma International
The governing body that stewards the ECMAScript standard, upon which JavaScript is based. 

## event handler
A function that is associated with an event listener and which is called when the event is triggered.

## executable file
A file that can be run directly on the computing hardware without requiring any interpretation or compilation at runtime.

## global
A global object is available at every scope and at every line of code. In JavaScript, the `Window` object is an example of a global object. Variables may be declared at a global or local scope level.

## hoisting
A feature of JavaScript where variables and functions may be referenced before they are declared without error. (See [this article on MDN](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) for additional details.)

## interpreter
An application used to convert source code in a given programming language into machine instructions that can be executed by the computing hardware.

## iterable objects
JavaScript objects that implement the [Iterator Protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) so they can be iterated over including Arrays, Maps, Objects, Symbols, and more. 

## linter
A tool used in a code editor to check syntax and style, usually in real-time. Most popular code editors support linting tools such as [JSHint](http://jshint.com/) and [ESLint](http://eslint.org/). Refer to the documentation in your chosen editor for more information about installing and using linters for whatever language you are writing.

## local
Local objects are only known within the scope where they are defined. This is typically limited to a code block between two curly braces. Local objects are often used within functions, loops, and conditionals for  specific tasks, and they may be named with generic names that are re-used in other local scope contexts.

## method
A function related to a Class object. Class objects are made up of data properties and methods that perform some behavior or action. The methods are the "verbs" of the Class.

## named function
A function that is declared with the `function functionName(){}` syntax. This function has a named reference that is available within its scope and context.

## property
A piece of data related to a Class or object. Objects are made up of data properties, which contain information describing the object, and methods, which perform some behavior or action. The properties are the "adjectives" of the object.

## scope
The context of the code, including all known object, function, and variable references, as it is executed by the interpreter.

## scripted language
A description of a programming language that uses a runtime interpreter to convert source code into an executable file.

## source code
The code a developer types in a given programming language using some form of text editor. This code is typically either compiled into an executable file, or it is interpreted at runtime by an interpreter.

## typed language
A description of a programming language that requires developers to explicitly declare the datatype of each variable they use.


