# Scope and Scoping


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

