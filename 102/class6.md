# Class 6 Reading Notes

*JavaScript(JS)* is a lightweightm interpreted, or just in time complied programming language with first class functions.

**Introduction to JavaScript - basic output**  
JavaScript can be used inside web browsers and on the server as well.
i.g. Node.js, or io.js  
**3 major parts of "JavaScript"**

- the language itself.
- the DOM API, how the language can interact with the various parts of a web page while in the browser.
- the server API, provied by one of the server-side system.

Any text editor can be used.
you can embed the JAvaScript code directly inside the HTML file.

**Alert**  
One of the most simple way to display text for the user (output), is using "alert" function.

**Document.write**  
this function is used to change the content of the page.

**Console.log**  
It is provided by most of the web browsers. It is an additional window which is normally not visible, where the browser can print out warnings and errors generated by the execution of the JavaScript code.  
console.log("Hello World");

**Promt**  
var name = prompt("Your name:", "");
document.write("Hello", name);

when user presses cancel or get out of the that format, the prompt() function will return null.

**Confirm**  
If the user presses OK the confirm() function will return true, otherwise it will return false. if confirm returned true, it will print "Hello World".  

**some keyterms**  
There are some basic key terms in javascript that we are going to use mostly.

- let => a variable that can be changed.
- const => a variable that will never change once it is declared
- var => an old way of declaring variable, must be used on old browsers before 2015.

[Back to home](../README.md)
