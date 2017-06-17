# Basic Syntax

JavaScript uses a specific syntax to write code. This allows the JavaScript interpreters in web browsers to properly parse and execute that code. Like with any programming language, JavaScript interpreters can be thrown off with even the slightest mistake in syntax. A misplaced comma (`,`) or missing curly brace (`}`) can make your entire program throw an error and fail to execute. 

These sorts of issues are often the most frustrating for new developers to deal with because they are difficult to find when they happen, and they represent a failure at the "easy" part of writing code (getting the punctuation correct). It often feels like the more difficult parts of writing code **should** be the large concepts and design techniques we struggle to grasp when we first learn them. But, in fact, much of the experience that comes with coding is about being able to scan through a set of lines and quickly pick out misplaced brackets, curly braces, parentheses, and commas. 

There are some ways to help grasp syntax more easily. It's always good to use a dedicated editor that includes a "linter". A linter is a tool that helps us see issues in the code we've written, especially from a stylistic and syntactical perspective. Linters are like grammar checkers for programming languages.

{% exercise %}
Create an alert box that says whatever you want.

{% initial %}
debugger;

{% solution %}
window.alert('Your Message Here');

{% validation %}
assert(true);


{% endexercise %}
