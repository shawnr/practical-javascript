# Controlling Logical Flow

In all programming languages, and in every program beyond the most basic set of instructions, it's crucial to control the flow of logic to achieve the desired result. Most programs are built to handle some task, and most of those tasks require the program logic to make decisions about what should be done next. The process of determining what instructions the program should execute next is one of the tasks we work hardest on as we write our code.

Imagine a situation where we have a website that requires users to be logged in and have a verified email address in order to use the features the site provides. This is a common case, and requires the application powering the website to determine a few things:

* Is the user currently logged in?

This seems like an easy question, and on one level it is: The user's login state could be represented with a Boolean (`true` or `false`). But in order to determine that, we've already decided at the very beginning of our application that we need to check if the user is logged in.

Let's imagine the user is not currently logged in. What next? We might move the user to a login page so they can login. Now we would encounter even more branching logic:

* Does the user have an account?
** If so, did the user provide the required credentials to login?
** If the credentials are bad, redirect the user to an account recovery screen.

