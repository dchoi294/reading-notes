# Class 9 Reading Note

## Stacks and Queues

A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.  

Common terminology for a stack is

Push - Nodes or items that are put into the stack are pushed  
Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.  
Top - This is the top of the stack.  
Peek - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.  
IsEmpty - returns true when stack is empty otherwise returns false.  

***concepts***  
First In Last Out (**FILO**)

This means that the first item added in the stack will be the last item popped out of the stack.

Last In First Out (**LIFO**)

This means that the last item added to the stack will be the first item popped out of the stack.  

The topmost item is denoted as the top. When you push something to the stack, it becomes the new top. When you pop something from the stack, you pop the current top and set the next top as top.next.

Push O(1)
Pushing a Node onto a stack will always be an O(1) operation. This is because it takes the same amount of time no matter how many Nodes (n) you have in the stack.

Common terminology for a queue is

Enqueue - Nodes or items that are added to the queue.  
Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.  
Front - This is the front/first Node of the queue.  
Rear - This is the rear/last Node of the queue.  
Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.  
IsEmpty - returns true when queue is empty otherwise returns false.  

First In First Out (**FIFO**)

This means that the first item in the queue will be the first item out of the queue.

Last In Last Out (**LILO**)

This means that the last item in the queue will be the last item out of the queue.

When you remove an item from a queue, you use the dequeue action. This is done with an O(1) operation in time because it doesn’t matter how many other items are in the queue, you are always just removing the front Node of the queue.  

Typically, you would check isEmpty before conducting a dequeue. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.  

Regerernce [Stacks and Queues](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)  

[Back to Home](../../README.md)
