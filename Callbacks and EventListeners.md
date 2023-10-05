Callback functions:

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/a70ddcb4-48a0-4b64-b544-7a66e4ec25f7)

We can pass a function as a param to another function. The function which is passed as argument is called the callback function.

Once we pass the function as an argument, its upto that function as to when to execute it.

Callbacks help us to do asynchronous tasks in JS which is a synchronous, single-threaded language.
setTimeout is an example for callback function. The function we pass as argument for setTimeout is a callback function.

Lets take the below example. We have debuggers placed in these 2 lines as shown.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/3f094e35-57a0-41ad-bff0-8aedf7fc4835)

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/60abfc9c-72ec-49f4-97c4-8c146a2c66ed)

When we run the code, we can see x and y are in call stack, the second image shows that the call stack is empty after x & y are executed. Then after 5 seconds, we can see the setTimeout function in call stack and then it gets executed.  

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/57494215-f134-4893-b3e5-4f127513809c)
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/028c911b-15dd-43f1-a2f2-caf96a2ee23c)
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/dac5f2c1-0f5c-4334-be89-cb35adc30951)

Call stack is also called the Main thread. We should not block the main thread, i.e. lets say if a function takes 20 to 30 seconds to complete an operation and since the engine has only one call stack, we will be "blocking the main thread". So to not do this, callbacks helps us to perform it asynchronously.


EventListeners:
Here, function passed to the event listener is a callback function. Same as mentioned above for asynchronous execution, this function pops into the call stack and gets executed when the button gets clicked.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/bb41da6c-8a70-410d-bec4-a44f5ea68fe3)


Closures with Event Listeners:
Let's say we need to print the count each time the button gets clicked. As in the below image, we've enclosed the eventListener inside a function with a count variable. So, now the eventListener forms a closure with attachEventListener function. We can see the function xyz in the call stack and in the Scope that it has access to Global and Closure scope with count variable.  

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/cf2f6325-ef99-44b5-91ed-65c33f85eb77)

Under the event listeners tab, we can see the closure and global scope under Scope dropdown as well.
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/14588ecb-ed30-46f5-8e48-b1172ec99ddb)


Garbage collectors and Event listeners:

Event listeners are heavy i.e it takes memory. Makes it impossible to free up the memory, when it forms a closure. This can make the page slow. So, we need to remove the event listener which helps to garbage collect the variables when not used.

