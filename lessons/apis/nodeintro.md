# Node Introduction
Node JS is going to be very, very different from any other programming languages you've used before. This is because Node uses relies on running code **asynchronous** as opposed to synchronously. Look at this example below:

```
ask the user for their name
upload the name to a database
tell them it is complete
show a menu
```

If the code above is run synchronously it would:

1. Ask the user for their name
1. Upload it to the database
1. Wait for the name to upload
1. Tell them it is complete
1. Show a menu

And if it was run asynchronously it would:

1. Ask the user for their name
1. Upload it to the database
1. Show the menu
1. Wait until the name has uploaded then tell them it is complete

You are probably still confused so if you just continue and if you get stuck just ask for help, but **in a nutshell Node runs code in a different order than other languages**.

Last thing, Node is very flexible. You can put semi-colons at the end of lines if you want to but they are not required. You don't have to put in the ones I have in my code, I just have a habit of doing it because it is good practice.
