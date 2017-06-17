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

## Practice with Comments
In order to test some of the things we've read on this page, complete the exercises below. 

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