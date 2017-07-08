# Strings

In most programming languages, the Data Type for what we would normally consider "text" is the String. Strings can contain any text (including numbers and symbols) that can be typed. Here are some examples:

```js
let x = 'Hello World!';
let y = "Hello World!";
let z = "中文 español deutsch English हिन्दी العربية português বাংলা русский 日本語 ਪੰਜਾਬੀ 한국어 தமிழ் עברית";
```
Each of the variables above has been assigned a value that is of the type "string". We can use either single quotes (`'`) or double quotes (`"`), but the quotes around our string must match. 

Strings may contain any amount of text desired, and sometimes it may be necessary to break a String value across multiple lines. There are two ways to do this. The first way uses the `+` sign to _concatenate_ each line:

```js
let longText = "This text is " +
    "very long and contains " +
    "many different characters.";
```
The other way to define long String values is to use the backslash character at the end of the line to indicate that the string will continue on the next line:

```js
let longText = "This text is \
    very long and contains \
    many different characters.";
```

## Escaping Characters
Although we can choose to use either single or double quotes to indicate a String, there are some things to consider when choosing between the two. A String defined with single quotes may contain double quotes without breaking the String. And a String defined with double quotes may contain a single quote (or apostrophe) without breaking the String. Sometimes it makes sense to selectively choose one or the other based on what the content of the String will be. Take a look at this example code:

```js
let a = "Today's Featured Video"; // The single quote can be used as an apostrophe because the String is defined with double quotes.

let b = 'The important critic said, "I love this app!"'; // The double quotes can be used because the single quotes are used to define the String.
```
In the example above, we can see that using single or double quotes can be advantageous for certain types of content. However, it's not the nicest style to switch between single and double quotes like this, and there are some characters that remain problematic within Strings regardless of which style of quote you choose.

Remember that backslash (`\`) we used to indicate a multi-line string? What if we need to make a string that contains backslashes? What if we have text that requires a mixture of double quotes and apostrophes? What if we want to add a carriage return or a tab to the String? Those characters are visible when we read them (they make blank space for us), but how do we even type them?

In order to solve this problem, we can **escape** characters in a String. Escaping is done by prefixing the character with a backslash (`\`). Here is an example:

```js
let a = 'Today\'s Featured Video'; // The apostrophe has been escaped using a backslash character.

let b = "The important critic said, \"I love this app!\""; // The double quotes have now been escaped with a backslash.
```
In the example above we can see that using the backslash allows us to choose which quotes we prefer regardless of the content of our String.

Another set of important characters to escape are [Unicode](https://en.wikipedia.org/wiki/Unicode) characters. If we wanted to insert a ❤ character in a String, then we would use the following code:

```js
let heart = "Here is a heart: \u2764"; // The backslash escapes the unicode character.
```
If we did not escape the [Unicode](https://unicode-table.com) value then our String would be "Here is a heart: u2764" instead of "Here is a heart: ❤".

We can find a full table showing how to escape characters on the MDN String page. Here it is for convenience:

| Code	                | Output                |
|-----------------------|---------------------|
| \0	                | the NULL character |
| \'	                | single quote |
| \"	                | double quote |
| \\	                | backslash |
| \n	                | new line |
| \r	                | carriage return |
| \v	                | vertical tab |
| \t	                | tab |
| \b	                | backspace |
| \f	                | form feed |
| \uXXXX	        | unicode codepoint |
| \xXX	                 | the Latin-1 character |



## Exercises
Please try working these exercises to practice some of the skills we've learned in this section.


{% exercise %}
Fix the String definition below so it works.

{% initial %}
let x = "Courage is not the absence of fear, 
    but rather the judgement that something 
    else is more important than fear.";

{% solution %}
let x = "Courage is not the absence of fear, \
    but rather the judgement that something \
    else is more important than fear.";


{% validation %}
assert(typeof(x)==="string");

{% endexercise %}

{% exercise %}
Fix the String so the text shows up properly.

{% initial %}
let x = "You will need a 3/8" socket for this job.";

{% solution %}
let x = "You will need a 3/8\" socket for this job.";

{% validation %}
assert(typeof(x)==="string");

{% endexercise %}

{% exercise %}
Fix the String so the text shows up properly.

{% initial %}
let x = 'All's I know is, my gut says, "Maybe"';

{% solution %}
let x = 'All\'s I know is, my gut says, "Maybe"';

{% validation %}
assert(typeof(x)==="string");

{% endexercise %}

{% exercise %}
Fix the String so the text shows up properly.

{% initial %}
let x = 'In Seattle we don't use an u2602.';

{% solution %}
let x = 'In Seattle we don\'t use an \u2602.';

{% validation %}
assert(typeof(x)==="string");

{% endexercise %}







