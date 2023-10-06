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


How Event Listeners work in JS?
Lets take the below example:

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/0cb9500e-cb4f-4a68-8366-40b750887088)

1. Global execution context gets created and pushed in the call stack.
2. Since first line is console log start, Start gets printed in console.
3. Then, it sees an eventListener which is a callback function when a click happens. So it registers the callback function in the Web API Environment, with the click event attached to it. This event listener in Web API env, stays there until we explicitly remove the event listener or close the browser. So, it just waits till the user performs a click on the element.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/5fad53b1-0e95-4897-91a2-b64df1dfd2d6)

4. Then, moves to the next line, prints End in the console log.
5. Global execution context gets popped off the call stack, as there is no more code to execute.
6. Now, when the element gets clicked the callback function gets pushed in the call back queue and waits for its turn to be executed.
7. Main work of Event loop is, it continuously monitors the call stack and call back queue. When the call stack is empty and when there is a function in call back queue, event loop moves it to the call stack so that it gets executed.
8. So, now the callback function gets executed and Callback gets printed in the console and the callback function gets removed from the callback queue.

Why do we need a callback queue?

Lets say user clicks on the button 7 to 8 times, and the callback function gets queued 7-8 times. Now each function will get executed one by one, when the call stack is empty. When there are multiple event listeners in a page, so if there is a queue, they all get a chance to get executed one by one. 


How fetch works?

Lets take the below example,

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/cbe3f91e-d2e5-4b37-b64d-28a97a7ea53d)

1. Start gets printed in the console.
2. cbT function gets registered in the WEB API environment with the 5s timer already started.
3. cbF function gets registered in the WEB API environment, till the netflix API returns a response.
4. Once the netflix api returns a data response, the callback function will be ready to be executed. If the api returns a response within 50ms, still the callback function cbF wont be pushed to the callback queue.

This is where the microTask queue comes into picture. MicroTask Queue has higher priority than callback queue. All the callback functions which comes through promises will go into the microTask queue. 

Mutation observer -> Mutation observer keeps checking if there is any mutation in the DOM tree (like attribute changes/ content changes etc). The callback function from a mutation observer goes into microTask queue as well. 

Everything else, such as callback from setTimeout / DOM APIs goes into callback queue. Callback queue is also called "Task queue".


![image](https://github.com/Gayathri229/JavaScript/assets/60467364/454b719e-b6d9-4dfe-903f-9a510471d4cc)

5. Now, the cbF function gets pushed in the MicroTask queue.
6. Let's say the timer expired as well, and the cbT function is ready to be executed as well, so this will be pushed in the callback queue.
7. Then, it moves to console log End line and prints it in the console.
8. Now, the cbF function from microTask queue gets moved to callstack and gets executed.
9. Then, the cbT function from callback queue gets moved to callstack and gets executed.


STARVATION OF CALLBACK QUEUE:
Let's say there are 2 tasks in microTask queue, and one task creates another microTask, and the newly created one creates another microTask and so on.... In this case, task inside callback queue doesn't get a chance to be executed or takes longer time to get executed as microTask queue has higher priority. This state is when starvation of callback queue occurs.




![image](https://github.com/Gayathri229/JavaScript/assets/60467364/f7acebc1-09f1-42fc-a6bf-35b82ba51601)


   
