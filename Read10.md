# Stack

A stack is a data structure that consists of Nodes. 

Each Node references the next Node in the stack, but does not reference its previous.

**Terminology:**
- Push: Nodes or items that are put into the stack are pushed
- Pop: Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
- Top: This is the top of the stack.
- Peek: When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.
- IsEmpty: returns true when stack is empty otherwise returns false.

**Stacks follow these concepts:**

*FILO*
First In Last Out

This means that the first item added in the stack will be the last item popped out of the stack.

*LIFO*
Last In First Out

This means that the last item added to the stack will be the first item popped out of the stack.

**Methods on Stack:**

*Push*

Pushing a Node onto a stack will always be an O(1) operation. This is because it takes the same amount of time no matter how many Nodes (n) you have in the stack.
1. Instantiate the Node that you want to add
2. Assign the next property of new Node to reference the same Node that is at the top
3. Re-assign our reference top to the newly added Node

*Pop*

Popping a Node off a stack is the action of removing a Node from the top. When conducting a pop, the top Node will be re-assigned to the Node that lives below and the top Node is returned to the user.
1. Create a reference named temp that points to the same Node that top points to.
2. Re-assign top to the value that the next property is referencing
3. Re-assign the next property of the node to be None
4. Return the value of the node that was popped off

*Peek*

When conducting a peek, you will only be inspecting the top Node of the stack.
- Return the value of the value of the top node

*Is Empty*
Check if stack is empty or not and return a boolean

# Queue

**Terminology:**
- Enqueue: Nodes or items that are added to the queue.
- Dequeue: Nodes or items that are removed from the queue. If called when the  queue is empty an exception will be raised.
- Front: This is the front/first Node of the queue.
- Rear: This is the rear/last Node of the queue.
- Peek: When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
- IsEmpty: returns true when queue is empty otherwise returns false.

**Queues follow these concepts:**

*FIFO*
First In First Out

This means that the first item in the queue will be the first item out of the queue.

*LILO*
Last In Last Out

This means that the last item in the queue will be the last item out of the queue.

**Methods on Queue:**

*Enqueue*

Adding items to the rear of the queue
This is done with an O(1) operation in time because it does not matter how many other items live in the queue (n); it takes the same amount of time to perform the operation.
1. Change the next property of the rear node to point to the Node we are adding
2. Re-assign the rear reference to point to new node

*Dequeue*

Removing items from the front of the queue
This is done with an O(1) operation in time because it doesn’t matter how many other items are in the queue, you are always just removing the front Node of the queue.

1. Create a temporary reference type named temp and have it point to the same Node that front is pointing too
2. Re-assign front to the next value that the Node front is referencing.
3. Re-assign the next property on the temp Node to null
4. Return the value of the temp Node that was just removed

*Peek*

When conducting a peek, you will only be inspecting the front Node of the queue.
- Return the value of the value of the front node

*Is Empty*
Check if queue is empty or not and return a boolean


