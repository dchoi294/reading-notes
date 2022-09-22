# Class 8 Reading Notes

## Expressions and operators

An expression is a valid unit of code that resolves to a value.  
**Two types of expressions**  
*those that have side effects such as assigning values*  
Example => x =7  
*those that purely evaluate*  
Example => 3 + 4  

**Assignment operators**  
It assigns a value to its left operand based on the value of its right operand.

**Assigning to properties**  
If an expression evaluates to an object, then the left-hand side of an assignment expression may make assignments to properties of that expression.  

>const obj = {};  

>obj.x = 3;  
>console.log(obj.x); // Prints 3.  
>console.log(obj); // Prints { x: 3 }.  

>const key = "y";  
>obj[key] = 5;  
>console.log(obj[key]); // Prints 5.  
>console.log(obj); // Prints { x: 3, y: 5 }.

If an expression does not evaluate to an object, the nassignments to properties of that expression do not assign.  

## Loops

**for statement**  
A for loop repeats until a specified condition evaluates to false.  
When it executes,

- initialExpression is executes
- conditionExpression is evaluated
- statement executes
- incrementExpression is executed
- Control returns to conditionExpression

**while statement**  
It executes its statements as long as a specified condition evaluates to true.  

while (condition)
  statement

If the condition becomes false, statement within the loop stops executing and control passes to the statement following the loop.

[Back to home](../README.md)
