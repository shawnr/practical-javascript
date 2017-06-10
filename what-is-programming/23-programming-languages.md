#Programming Languages

Programming languages have developed alongside computing hardware in order to facilitate different approaches to writing software. What is a programming language, exactly? A programming language is a "notation for writing programs, which are specifications of a computation or algorithm" ([Wikipedia](https://en.wikipedia.org/wiki/Programming_language)). It is the _way_ we tell the computing hardware what we want it to do.

Sometimes programming languages were constrained by the capabilities of their target hardware. Other times, these languages were tailored to specific types of calculations or algorithms in order to more easily accomplish their users' goals. This book deals primarily with JavaScript, but the following list will help you gain an understanding of some of the many types of programming languages. Please note that this list is in no way exhaustive.


## Assembly

The very first programming languages were Assembly Languages. These are "low level" languages, meaning that the developer writes instructions that are directly executed by the computing hardware. This often means that developers typed cryptic sequences of characters or otherwise indicated binary information that often corresponded directly with how the hardware worked.

* [Assembly Language](https://en.wikipedia.org/wiki/Assembly_language)

## Compiled Languages

Writing Assembly code is so arduous that developers almost instantly wished for a more expressive way to write their software. This quickly led to the development of "[compiled](https://en.wikipedia.org/wiki/Compiler)" programming languages. The developer would write code in a "higher level" language that corresponded less to the machine instructions and more to the way humans think and speak. Those instructions were then interpreted by a compiler, which would produce a "binary" file that could be executed by the computing hardware. These languages remain popular, and new compiled languages are regularly created, because they allow for a good balance of developer experience and machine efficiency.

* [Fortran](https://en.wikipedia.org/wiki/Fortran)
* [COBOL](https://en.wikipedia.org/wiki/COBOL)
* [C++](https://en.wikipedia.org/wiki/C%2B%2B)

## Scripted Languages

Although compiled languages still thrive in the modern software ecosystem, there has been a distinct rise in the past few decades of "scripted" programming languages. These languages are "interpreted" or "compiled" at runtime, skipping the step of compilation and the creation of a binary file. This is handy for developers who want to see their code execute as quickly as possible during development, and thanks to the strength of modern computing hardware these languages are able to perform well for their tasks. Many websites are built using scripted languages (Facebook, Instagram, etc.), and many applications use embedded scripted language interpreters to allow users to enhance their work (such as Flash, or World of Warcraft). Scripted languages are some of the most popular in the world right now.

* [Python](https://en.wikipedia.org/wiki/Python_%28programming_language%29)
* [PHP](https://en.wikipedia.org/wiki/PHP)
* [JavaScript](https://en.wikipedia.org/wiki/JavaScript)
* [Ruby](https://en.wikipedia.org/wiki/Ruby_%28programming_language%29)

## Typed Languages

Data management is such a significant part of programming that languages are often grouped based on whether or not they require developers to "declare" the datatype of the variables they use. This means that if you declare a variable `foo` is an `integer` then it could be equal to `1`, `2`, or `3`, but it cannot be equal to `"bar"`. Languages that require developers to say that a variable is going to be a specific type of data are called "typed" and are valued for their ability to help prevent the errors that are caught by "type enforcement."

* [C++](https://en.wikipedia.org/wiki/C%2B%2B)
* [Java](https://en.wikipedia.org/wiki/Java_%28programming_language%29)
* [Go](https://en.wikipedia.org/wiki/Go_%28programming_language%29)
* [Swift](https://en.wikipedia.org/wiki/Swift_%28programming_language%29)

## Dynamic Languages

Dynamic languages allow developers to alter the type of a variable in mid-usage, and they do not require the developer to declare the datatype. This means that if a variable `foo` is defined, then `foo` could be equal to `1`, `2`, or `"bar"` at any point in the execution of the code. This is often seen as beneficial because it allows developers to be more free-form with how they handle data and does not require the same rigid foresight as a typed language.

* [Python](https://en.wikipedia.org/wiki/Python_%28programming_language%29)
* [PHP](https://en.wikipedia.org/wiki/PHP)
* [JavaScript](https://en.wikipedia.org/wiki/JavaScript)
* [Ruby](https://en.wikipedia.org/wiki/Ruby_%28programming_language%29)

## Functional Languages, Object Oriented Languages, etc.

There are many [ways to group programming languages](https://en.wikipedia.org/wiki/History_of_programming_languages), and the more we learn about programming languages then the easier it is to appreciate the differences between languages. Some differences, such as "functional programming" or "object oriented programming" (OOP) are difficult to grasp unless you know something about how languages work. For the sake of this historical introduction I'm going to skip over all of these very interesting and super useful languages and what makes them unique. Nonetheless, you may be curious to look into them more deeply.

* [Scala (functional)](https://en.wikipedia.org/wiki/Scala_%28programming_language%29)
* [Clojure (functional)](https://en.wikipedia.org/wiki/Clojure)
* [Haskell (strongly typed)](https://en.wikipedia.org/wiki/Haskell_%28programming_language%29)
* [R (statistical programming)](https://en.wikipedia.org/wiki/R_%28programming_language%29)
* [Lisp (lots of parentheses)](https://en.wikipedia.org/wiki/Lisp_%28programming_language%29)

