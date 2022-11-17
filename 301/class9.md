# Class 9 Reading Note

What is functional programming?

- a programming paradigm that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.

What is a pure function and how do we know if something is a pure 
function?

- A function that always returns the same result if given the same arguments, and it does not cause any observable side effects.

What are the benefits of a pure function?

- encourage safe ways of programming, and guarantees that they will not modify anything outside their body.

What is immutability?

- Unchanging over time or unable to be changed. In JS, when data is immutable, its state cannot change after it's created.

What is Referential transparency?

- pure functions + immutable data = referential transparency, which results that methods always returning the same value for the given argument without any side effects.

Reference [Functional Programming Concepts](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)  

What is a module?

- a file containing related code.

What does the word ‘require’ do?

- reads, executes, and proceeds JS file to return the exports object.

How do we bring another module into the file that we are working in?

- let express = require("express");

What do we have to do to make a module available?

- set variable, make it require, and  module exports

Reference [Node JS Tutorial for Beginners #6 - Modules and require()](https://www.youtube.com/watch?v=xHLd36QoS4k&ab_channel=TheNetNinja)  

[Back to Home](../../README.md)  
