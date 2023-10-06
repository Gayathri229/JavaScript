JS has only one call stack and it is present in the JavaScript engine. The whole code runs in the call stack.
When we run a code, a Global Execution context is created and pushed inside the call stack.

Whatever is pushed into the call stack is executed then and there. It doesn't and cannot wait for anything.

WEB APIs in JS:

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/c93531ad-2f76-4520-a3ec-9a746595ae8e)

Browser has these super powers like access to timer, local storage, location, website, url etc. If JS Engine needs access to these super powers, it is through "WEB APIs".
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/040076aa-ea99-4467-bd86-a4c4596effa4)

These Web APIs are part of browser. Browser gives access to use these super powers in the JS Engine/Call stack. We will be able to access these through a "Global Object" which is the keyword "window". Say, window.setTimeout, window.console.log etc.
Since the WEB APIs are present in the global scope we can use them without the window keyword. 
So the browser wraps these WEB APIs into a Global Object - window and gives access to this window for JS Engine to use it. 
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/41ca3b50-07cd-484b-a3fe-9976d8738093)


How setTimeout works behind the scenes? [CALLBACK QUEUE AND EVENT LOOP]

Let's take this function for execution for example,
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/b4b6ba61-8447-4d19-aeba-9e686a4f8018)

1. A Global execution context is created and pushed into call stack.
2. Since the first line is console.log, it calls console Web API, which internally makes another call to print something in the console. This console API is plugged to your code through window object. // Start gets printed in console
3. In setTimeout function, we are using setTimeout API. Here when it sees a callback function, it registers a callback function and starts the timer of 5000ms. And proceeds to execute the next line. Note: It doesnt wait here.
4. Executes the End console print line.
5. Now, the Global Execution context pops off the call stack. Note: The timer is still running
6. Now, we need the callback function in the callstack for it to be executed once the timer is over.
7. Here, the callback queue and event loop comes into picture.
8. Once the timer expires, the callback function is put inside the callback queue.
9. Event loop checks the callback queue and puts it inside the call stack. It keeps checking if we have something in the callback queue.
10. Now, Global execution context is created and the callback function gets pushed into callstack and gets executed. Callback gets printed in the console.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/048018a2-d24f-4344-bb38-fe8712944f48)

