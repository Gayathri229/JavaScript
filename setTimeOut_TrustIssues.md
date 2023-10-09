Let's take the below example, where there are a million lines of code which takes 10 seconds to execute, after printing End. 
Eventhough, we have given 5 secs for callback function, it executes it only after 10seconds because till then the Global Execution Context will still be in call stack executing the million lines of code. And Event loop keeps checking for the call stack to get empty till those lines are executed so that it doesn't "block the main thread". Only when the GEC is popped out the callback function is popped into call stack. This is called the "Concurrency model".

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/c2f9f27c-ada7-41dc-b370-29e08c0f58f2)

Example to block the main thread for 10s and check if callback is printed after 10s instead of 5s
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/09a4aad0-0ecc-4feb-a2cc-f4cdeb38eaa7)


This scenario doesn't occur is our day-to-day coding. This is why we shouldn't block the main thread and that is when the callback functions get a chance to get executed. 

setTimeout(0):
Let's take the below example. Just because the timeout is 0ms doesn't mean it'll be executed like other lines of code. It will be registered in the Web API environment as soon as it sees the callback function and has to come through the callback queue, then to the call stack once the GEC is out of the call stack.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/54314cc9-2208-476e-b965-40631be1d523)

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/e88c8d6b-c048-4ca7-a04c-dd5f56da5a11)

