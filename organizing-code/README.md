# Organizing Code

So far we have looked at code that represents basically step-by-step instructions. Loops provide a small way to re-use the same instructions, but for the most part we've focused in linear instructions where each line executes once. This is the base of programming, but it is not the most efficient way to write programs.

All programming languages allow for us to create groupings of code that can be executed on-demand. This means that we can write instructions that can be called to execute at various times in our program. By organizing our code into re-usable blocks, we can write more efficient code that is more easily maintained. Most languages call the fundamental form of this code grouping "functions" or "subroutines".

In JavaScript, we often use ["functions"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) to accomplish this goal. The JavaScript function is a powerful way to label and contain a block of instructions that can be accessed from throughout the program. Functions operate as small programs within the larger program.

## Impact on Code Organization

Functions allow us to organize code in more logical ways. The main body of our program becomes a set of higher-level instructions about what happens at runtime, and then each function will define more detailed instructions for each of those steps. We can group logic into well-named functions in order to provide a more clear presentation of our code for ourselves and other developers to read.

It's not unusual to have a function for each step of a process such as `login()` or `logout()`. Those two functions could be accessed from several places, but we never need to duplicate the lines of code within those functions. This means that if I were a developer who wanted to change something in the login process, I could look for the `login()` function and focus my attention there. There is no need to read through the entire program in order to find the lines that make logins work.

This also allows us to group logic in such a way that we can better account for missing data or logic that should not be run unless certain situations arise. It would be impossible to have a direct execution of code that both logs users in and logs users out. We need to execute those instructions at very specific times. Without functions we would be unable to manage even the most common of cases in our web applications.

## Impact on Maintenance and Enhancements

As mentioned before, functions help us eliminate duplication within our code and make it more clear what blocks of code actually do. This has a huge impact on both long-term maintenance and building enhancements. If the API provider for ecommerce transactions changes their API, then we only need to change the functions that handle the transactions, and we can easily identify where that code lives based on names and grouping. Without proper organization, code becomes like "spaghetti": We can't tell where one feature starts or ends, and we can't change one part without affecting all the stuff jumbled around it. We seek to make our code more like a well-organized shelving unit: Parts that go together live together, and we can easily access one part of our code without jostling around everything else.

By using functions to help us organize code, we make all of our development tasks easier and we increase the reliability of our application for our end users. 

<div class="tip-box">

<h3>Writing DRY Code</h3>

<p>A popular axiom among developers is to "Keep it DRY," or to "Write DRY code." In these sayings, developers are referring to the acronym D-R-Y, which stands for <a href="https://en.wikipedia.org/wiki/Don%27t_repeat_yourself">"Don't Repeat Yourself"</a>. The label stems from the book <a href="https://en.wikipedia.org/wiki/The_Pragmatic_Programmer"><i>The Pragmatic Programmer</i></a> (1999) by Andy Hunt and Dave Thomas, in which they write,  "Every piece of knowledge must have a single, unambiguous, authoritative representation within a system." This directive gets at the problem of creating confusing, redundant code or data systems that become ambiguous and where logic is tangled together.</p>

<p>Ideally, we could change any one part of our programs without having to change every other part. This is the core of the DRY principle. This is also related to the "separation of concerns" that we discuss occasionally. Each feature of a program should be as self-contained as possible, and we should strive to build clean points of integration to allow our different pieces to work together effectively.</p>

</div>