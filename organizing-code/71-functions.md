# Functions

As mentioned previously, [functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) are subroutines that can be executed whenever they are needed in our code. They are self-contained blocks of code, so they are convenient for creating "tools" or "components" that do just one thing. If we make a function that performs the "capitalize text" task, then anytime we need text capitalized in our program we can call that function.

## Function Syntax

## Function Arguments

## Returning Data From Functions

{% exercise %}
Define an a `for` loop that would double (multiply times two) `foo` 12 times.

{% initial %}
var foo = 2;
for ( ){
    
}

{% solution %}
var foo = 2;
for (let i=0; i<12; i++){
    foo = foo * 2;
    console.log(`Foo equals ${foo}.`);
}

{% validation %}
assert(foo==8192, "Incorrect.");

{% endexercise %}

