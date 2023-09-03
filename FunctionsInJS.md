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


Behind the scenes when running the code from chrome terminal:

<img width="204" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/3bf3f532-39fd-4314-9398-8075ec35a516">


<img width="1288" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/70bc3a5e-6476-4b00-a20e-ef044c424672">
<img width="197" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/ad4a23b4-2779-4e4f-9976-7983ad2bf06e">


<img width="1287" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/209f7f7e-ee44-448a-a646-3749bb7bed78">

<img width="1289" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/10b0dde0-873c-4399-b149-cd917ecf1810">
x is undefined in local scope

<img width="1291" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/1eb83e7d-c456-436f-9b32-2e9e2d5e8982">

After the whole code got executed, even the Global Execution context got popped out of call stack
<img width="1292" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/37cf625e-6a5d-4b35-9684-a4599d07035a">



