Functions

<img width="351" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/8be604d2-742d-4949-a85a-4ffdfbde8f58">

So as we know already, when this code is executed, Global Execution Context is created and pushed into the call stack. And when the function is called
another new execution context is created and pushed into the call stack and the control is shifted to the function now i.e line no 7. Here, in the function x should be considered as a new variable, when memory or 
value is allocated.

In the code execution phase, in line no 8, for console.log line, it will look for the value of x in the local memory space i.e value of x in that 
execution context, so here it is x = 10.
Now, this execution context is deleted from the call stack and control goes back to line 2.

Now, same happens for function b() as function a()

<img width="785" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/3e69964b-af33-4195-9c08-cac0a954cde6">

Now control goes back to line 3. Execution context looks like this after the two functions was executed i.e functions got popped out of Global execution
context after being executed.

<img width="806" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/03685b7f-611a-47bc-b4f1-387802d1fba4">

Now line 4 gets executed, here when it looks for value of x it in local space or in that particular execution context, x = 1


