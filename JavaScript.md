# JavaScript

Notes from Akshay Saini YT channel:

_**Javascript is a synchronous single-threaded language.**_

single-threaded -> can execute only one command at a time.
Synchronous -> can execute commands only in a specific order [completes one line and then only goes to the other].

So, Javascript can execute only one command at a time and in a specific order.

Let's see what happens at the back of the JS code we write:

Everything in java script happens inside an Execution context. Imagine execution context as a container / a box with 2 components in it. 

It gets stored as 2 components. Variable environment(Memory) and Thread of execution(Code).

<img width="1025" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/2003fee3-fc3a-4c51-a7aa-28aa8a70ada6">

Variable environment(Memory) -> Here, the variables and functions get stored as {key: value} pairs.

Eg:
a : 10;
Fn: { ... }

Thread of execution(Code) -> Here, code gets executed one line at a time.

Eg:
.
--------
.
--------
.
--------



What happens when you run a javascript code?

When a Javascript code is run, an execution context is created. Let's take the below code for example:

<img width="535" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/00cac1ed-40a4-442c-b146-83efd0b10c73">

So as we know there are 2 components in an execution context. It gets created in 2 phases happen -> memory creation and code execution.

In phase 1, Javascript allocates memory to variables and functions. For variables, undefined is stored in the first place and for functions the whole code gets stored.

<img width="647" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/3e413220-9fc4-4087-8a69-6427623de13c">

In phase 2, i.e code execution, java script runs through the whole program line by line, and executes it.
As soon as it encounters line 1, it places the value 2 for n in the place of undefined.
<img width="635" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/a4f1b90e-e841-4bc4-8cb0-fff20fa65172">

line 2 to 5 is a function, so it has nothing to do here
line 6, is a function invocation. These are like mini programs and now a whole new execution context is created.
[ Functions are the heart of Javascript. ]

<img width="633" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/ffe53291-7a60-4c62-921e-ffeec605d6a4">

Now again, memory creation phase takes place for the function -> phase 1.
Here it includes allocating memory for parameters too.

<img width="582" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/f85dee33-9e32-404d-8209-d991efc92671">

2 gets passed to n, and num will be assigned with 2 when function gets called.

line 3, code execution happens, ans = num * num, 2 * 2 = 4 gets assigned to "ans".

line 4, we encounter the special keyword, it tells the function, to return the whole control back to where the function was invoked.
<img width="661" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/4a8a5f50-099b-4586-93e8-8e389fc48c5f">

When the whole function is done executed, the execution context of the function will be deleted once the value is returned.

control goes to line 6 again. Now square2 gets assigned with 4.

Now in line 7, a function invoke happens and again execution context is created.
<img width="616" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/1eebef41-9d9f-4241-af30-9415849bc5c4">

again num and ans gets assigned with undefined. 

As n = 4 now, num gets assigned as 4, and ans becomes 4 * 4 = 16.

ans gets returned, and square4 gets assigned with 16.

<img width="588" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/fd623705-5c77-444c-99e4-7ca4876dc337">



To handle the execution context creation, deletion and control, Java script manages a stack i.e a call stack. 

So whenever a Java script program is run, this call stack is populated with Global execution context. i.e the first execution context that gets created when a program is run. 

<img width="285" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/f5f718cd-8181-40b1-bb4f-fba1cf846707">


When it encounters a function and another execution context is created, this execution context moves into the stack and is popped out when the execution of the method is done and control goes back to the global execution context.

<img width="289" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/9a420c92-d5d4-48bf-b531-2009d75ad1f9">

<img width="287" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/7eda9435-9de1-426a-b7f6-eac9ec38d847">

Below shows how call stack works, when the code in the image is run
<img width="556" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/404dc147-b625-4a40-aef9-ca1ffb826dea">

Call stack is also known by the below names:

<img width="918" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/d53ddc2d-6dd7-47fc-b3c3-a928984ebe03">


