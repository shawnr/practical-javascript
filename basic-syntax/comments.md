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

   apiDomain = Domain of the API endpoint.
   apiPort = Port for the API endpoint.
   apiVersion = Version of the API to use.
   apiBasePath = The path for the API used throughout this app.
*/

let apiDOMAIN = "api.example.com"; 
let apiPort = 8080; 
let apiVersion = "1.3"; 

let apiBasePath = `http://${apiURL}:${apiPort}/${apiVersion}/`;

```

{% exercise %}
Define a variable `x` equal to 10.

{% initial %}
var x =

{% solution %}
var x = 10;

{% validation %}
assert(x == 10);

{% context %}
// This is context code available everywhere
// The user will be able to evaluate `exposedVar`
var exposedVar = 3;
// ... or call `exposedFunction`

{% endexercise %}