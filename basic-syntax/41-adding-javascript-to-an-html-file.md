# Adding JavaScript to an HTML File

JavaScript is related to an HTML file using the `<script>` tag.

## Embedded JavaScript

## External JavaScript

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