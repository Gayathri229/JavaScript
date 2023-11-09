ASYNC:  
  
Async is a KEYWORD that is written before a function to make it an async function.  
Async function always returns a promise. If we don't return a Promise, it'll take the value, wrap it inside a promise, and then return the Promise.  
Eg:  Returns a String  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/f3bc18f1-da34-44a3-97eb-dd0c86203062)  
  
Output:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/6e3c08db-395e-46a3-b6f5-f6b5d697727c)

Eg: Returns a Promise  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/f67613ea-9de9-4a00-b929-8caee9d4ba49)

Output:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/5e8a35df-9c87-4bce-aea2-a10ba721b4b0)

Using Async with Await:  
  
Async Await combo is used to handle Promises. 
Await is a keyword that can be used only inside an Async function.
We write the Await keyword in front of a Promise. And it resolves the Promise.  

Without Await:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/a8074504-c005-4aef-afda-8bdd9da96595)

With Await:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/a375e3ef-09fe-4eab-9f04-0c132619f125)  

Let's set a timeout while resolving the Promise, and see what happens here  

Eg: Without using await  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/f35bc059-08bf-4cbe-a676-163d1ef59488)  

Output: Here we could see that Namaste Javascript was printed first, then after 10s Promise was resolved.  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/dc5b027e-5885-4c6d-a4fb-d2a4b9ec014f)  

Eg: With using Await  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/46d1a78f-a75d-449d-8158-c42d05b879b1)  

Output:  Here, we can see that Promise resolved is printed first, then Namaste Javascript. So here, JS engine waits for 10s till the promise is resolved.  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/52f070e9-0d2e-4510-a620-9e11b902a925)

If we have a line above the await, that line will be printed immediately without any wait, but the lines below await are printed only after the wait time i.e. 10s
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/002f9152-2f12-4a1d-b924-bb70dc7cb188)  

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/cf0adc44-7636-4cbf-a03b-3f935bf505a5)
  
  
Let's see an example where we have to resolve one promise twice:  

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/0e6ec9db-3a4b-46d7-bccf-5977ec654e1f)  

Output:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/9c2fb9a4-e81a-444a-aa27-1885d34c06c2)  

Explanation:    
So, let's take an example where we have to resolve the same promise twice. The promise has a wait time of 10 seconds. As we are resolving the same promise twice, it means we have to wait for the same time to resolve both promises. So, when we run the program, Hello world gets printed first, as there is no await before that line. And in line number 11, the function gets suspended and gets removed from call stack. After 10 seconds, the function gets back into callstack after the promise is resolved and prints both values val and val2. This is because both of them have the same wait time and it has already waited 10s to resolve the first promise. So, behind the scenes the call stack is not blocked by the handlePromise method instead it gets suspended each time it sees a await keyword and gets back in after the time is over. 


Let's take another example where we have to resolve 2 different promises, p1 with 5s, p2 with 10s

Here, p1 gets printed first, then the function gets suspended for the next 5secs, and then in 5s the second promise gets resolved.

What if we had 2 different promises with, p1-10s, p2-5s?  
  
Since, the function would've already got suspended for 10s for p1, so it doesn't wait for another 5s, as the 5s got already included in the 10s suspension. It just prints both the values right after p1 gets resolved. 


