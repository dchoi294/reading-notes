# Class 5 Reading Note

What is the single responsibility principle and how does it apply to components?

- It is a technique that let you know if you should create a new function or object.

What does it mean to build a ‘static’ version of your application?

- A lot of typing and no thinking, and adding interactivity requires a lot of thinking and not a lot of typing.

Once you have a static application, what do you need to add?

- 

What are the three questions you can ask to determine if something is state?

- If it is passed in from a parent via props, remains unchanged over time, and can't compute it based on any other state or props in your component.

How can you identify where state needs to live?

- The common owner component

Reference [React Docs - Thinking in React](https://reactjs.org/docs/thinking-in-react.html)  

What is a “higher-order function”?

- Functions that operate ono other functions, either by taking them as arguments or by returning them.

Explore the greaterThan function as defined in the reading. In your own words, what is line 2 of this function doing?

- returning a boolean that checks if the received variable is greater than the varible it was set.

Explain how either map or reduce operates, with regards to higher-order functions.

- Since both operate math for us on the other side of the function, they are higher-order functions.

Reference [Higher-Order Functions](https://eloquentjavascript.net/05_higher_order.html#h_xxCc98lOBK)  

## Things I want to know more about

- Can we make our own higher-order functions and save them so that everyone can use them, too?

[Back to Home](../../README.md)
