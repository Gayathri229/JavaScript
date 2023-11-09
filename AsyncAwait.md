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

Output:  Here, we can see that Promise resolved is printed first, then Namaste Javascript. So here, JS engine waits 10s till the promise is resolved.  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/52f070e9-0d2e-4510-a620-9e11b902a925)

