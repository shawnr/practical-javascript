# Controlling Logical Flow

In all programming languages, and in every program beyond the most basic set of instructions, it's crucial to control the flow of logic to achieve the desired result. Most programs are built to handle some task, and most of those tasks require the program logic to make decisions about what should be done next. The process of determining what instructions the program should execute next is one of the tasks we work hardest on as we write our code.

## A Big Example

Imagine a situation where we have a website that requires users to be logged in and have a verified email address in order to use the features the site provides. This is a common case, and requires the application powering the website to determine a few things:

* Is the user currently logged in?

This seems like an easy question, and on one level it is: The user's login state could be represented with a Boolean (`true` or `false`). But in order to determine that, we've already decided at the very beginning of our application that we need to check if the user is logged in.

Let's imagine the user is not currently logged in. What next? We might move the user to a login page so they can login. Now we would encounter even more branching logic:

* Does the user have an account?
    * If so, did the user provide the required credentials to login?
        * If yes, then did the user verify their email?
            * If they *did* verify their email, then we can finally move them into the app.
            * If they did *not yet* verify their email, then we need to move into the email verification logic.
    * If the credentials are bad, redirect the user to an account recovery screen.

But all of that is assuming the user has an account. What if that's not the case? If the user has not yet created an account, then we know we must go through the account registration *and* the email verification process before allowing the user to access the website. 

## A Smaller Example

All of the decisions about big picture things like "user registration and verification" can be overwhelming to think about for novice developers. There are a lot of parts to the puzzle, and depending on the business logic (the rules and policies governing business operations) they can be more or less complicated. However, we encounter the need for logical flow control in many smaller ways, too.

Imagine that we're writing a page that fetches the posts from a blog. The data might be retrieved from a database or API, but once it has been fetched it's up to our application code to process the information into something that can be read by a user. In order to do this, we must properly insert the data into an HTML template for processing by the web browser.

We typically use a loop to process sets of data. Within the loop we might even need to do some checking in order to determine different aspects of the presentation, but in general we would be controlling our logical flow sort of like this:

* Got data. Begin processing.
* Process output of an item.
* Is there another item?
    * If so, process the next item.
    * If not, stop looping and move on to next section of code.

This kind of processing is very common and used in large and small ways. Within a loop to present content items there might be smaller loops to, perhaps, display each tag associated with the content, or to list each author on the content.

Controlling logical flow through different parts of our programs is an essential part of development. In this section we will explore the concepts of conditionals and loops to control logical flow.

