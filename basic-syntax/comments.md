# Comments

All programming languages allow developers to make "comments" on their code. Comments are non-functional lines that are meant to explain the logic of the code to our future selves or other developers. We use comments to make it clear why something is happening, how some component in our code should be used, or other details we wish to note for people reading our source code in the future. 

Comments are essential for properly documenting our code and explaining how it works. We usually work in teams, so what seems obvious to one person will almost never be obvious to another. It's crucial to learn to comment well and to use comments strategically to enhance the readability of our code.

## One-line Comments

One way of writing JavaScript comments is to precede any line with two slashes (`//`). This indicates that whatever follows is a comment and should not be executed by the interpreter. Here is an example:

```js
// Declare a variable called "foo" and set it equal to 12.
let foo = 12;
```

We can use this format to comment _parts_ of a line, too:

```js
// Set up API details
let apiDOMAIN = "api.example.com"; // Domain of API endpoint.
let apiPort = 8080; // Port for API endpoint.
let apiVersion = "1.3"; // Specify API version.

// Combine API details into base path for API.
let apiBasePath = `http://${apiURL}:${apiPort}/${apiVersion}/`;
```
As we see above, we can combine one-line and partial-line comments however we'd like. The key is to maintain readability and to use comments to help other developers understand the code more fully.

## Multi-line Comments

Multi-line comments have opening and closing symbols. They begin with `/*` and they end with `*/`. This style is often used when a comment needs to stretch across different lines. Sometimes this is necessary because of how much information needs to be conveyed, but it's often used to simply enhance the presentation of the code and provide more clear documentation.

Rewriting our example from above, we might see something like this:

```js
/* API Details

   These details should be configured per deployment. Additional
   information can be found in the runbook.

   apiDomain   =  Domain of the API endpoint.
   apiPort     =  Port for the API endpoint.
   apiVersion  =  Version of the API to use.
   apiBasePath =  The path for the API used throughout this app.
*/

let apiDOMAIN = "api.example.com"; 
let apiPort = 8080; 
let apiVersion = "1.3"; 

let apiBasePath = `http://${apiURL}:${apiPort}/${apiVersion}/`;
```

The multi-line comments are able to contain a much larger block of text, and we can use any simple text formatting we want to make the content of the comments more readable. Many developers will use some ASCII art to make their most important comments stand out.

## Commenting Out Code

Both styles of comment can be useful when trying to debug code. It's often necessary to remove a line of code when trying to track down problems with your program. However, we usually don't want to just delete the line and risk losing our work. In these cases, commenting out lines can be very helpful.

Here is what it looks like to comment out a line using the one-line comment format:

```js
// let titleHeading = document.querySelector("#title");
titleHeading.innerHTML = "Hello World!";
```

The first line of that code has been commented out. We could accomplish the same thing with multi-line comments (even though it's just one line):

```js
/* let titleHeading = document.querySelector("#title"); */
titleHeading.innerHTML = "Hello World!";

```

But we could also use the multi-line comment to comment out both lines:

```js
/* let titleHeading = document.querySelector("#title");
titleHeading.innerHTML = "Hello World!"; */
```

<div class="tip-box">

<h3>TODO: Make the Most of Comments</h3>

<p>In any program, comments are probably used for a few specific reasons. One is to document what the code is doing in plain language that can be more quickly understood by collaborators. Another is to sketch out ideas in "pseudocode" so we can better understand what tasks we need the code to accomplish. We often use different commenting conventions to allow for comments to be understood by machines, usually in order to generate "automatic documentation". Some of the popular packages that can make comments into usable documentation include <a href="http://warpspire.com/kss/">KSS</a> and <a href="https://github.com/dtao/autodoc">Autodoc</a> and <a href="https://en.wikipedia.org/wiki/Comparison_of_documentation_generators">a lot more</a>.</p>

<p>One of the most common ways to use comments is to track tasks yet to be completed with the phrase "TODO". This is done so that small tasks can be tracked in place. A developer can run a "find in files" search from their IDE or text editor to see all of the TODO notes across their code. By writing TODOs directly into the code, it's easy to see where functionality may be missing or temporary. When the next wave of improvements is made to the code, hopefully some of the TODOs will be completed.</p>

<p>When making notes like this in our code, it's critical to update the status of TODO notes. One of the worst things in a developer's day is to come across a TODO that is actually already implemented. In order to figure that out, we must review the code in detail, and it can be exceptionally confusing. We must be sure to note when our TODOs become TODONE, and we should remove those comments and replace them with more useful comments that help another developer understand the code more quickly.</p>

</div>



## Exercises
Please try working these exercises to practice some of the skills we've learned in this section. 

{% exercise %}
Mark the comment with one-line (<code>//</code>) syntax.

{% initial %}
Comment me out or I'll cause an error!

{% solution %}
// Comment me out or I'll cause an error!

{% validation %}
assert(true);

{% endexercise %}

{% exercise %}
Mark the comment with multi-line (<code>/*</code>) syntax.

{% initial %}
Comment both of these lines out 
or we'll cause an error!

{% solution %}
/* Comment both of these lines out 
or we'll cause an error! */

{% validation %}
assert(true);

{% endexercise %}

{% exercise %}
Comment out the broken line below using either form of commenting.

{% initial %}
let foo { bar };

{% solution %}
// let foo { bar };

{% validation %}
assert(true);

{% endexercise %}