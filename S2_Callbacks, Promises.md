Callback functions help to handle async operations in JS. 

Let's say we are placing an order in an e-commerce website. So it goes like this, we add items to the cart, proceed to payment, show the order summary to us, and deduct the amount from the wallet.  
But we don't know how much time will it take for the user to proceed to payment from cart, since time is unknown for proceed payment, order summary and deducting wallet time is also unknown.  
So, we put these in callback methods so that it can get executed asynchronously. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/628f6599-c2df-43e2-9994-e7508a3a07c7)

Here, we can see there is a callback function inside another callback function, and so on(nested callbacks). This grows the code horizontally instead of vertically. This is called Callback hell.  
This structure is called the Pyramid of Doom.  

Also, now it is the job of createOrder to call the proceed to payment and this chain continues to all callback methods i.e. proceed to payment is responsible for calling show summary, show summary is responsible for calling update wallet amount. This means the control of code is given to createOrder API. [Inversion of control]


Inversion of Control:  
As mentioned previously, when we lose control of our code when using callbacks we never know if the piece of code gets executed or not, or whether will it get executed properly without any errors/bugs. 



So, the 2 issues we face when using callbacks is 
- Callback hell
- Inversion of control


Promises: [Consuming Promises]  

Promises are used to handle async operations in JavaScript.

So, to handle Inversion of control, we call the createOrder API and assign it to a promise. A Promise is nothing but an empty/undefined Object. When the create order API gets executed(in any amount of time) it returns the value and fills the Empty/Undefined Object after any async time it takes.

then() is a function available with the Promise object. We ATTACH the callback function to the Promise Object. Once the promise object is filled, this call-back function will automatically be called.  
So Promise guarantees that the callback function will be called 100% of the time as soon as the Object is filled and will be called ONLY ONCE. Promise objects are immutable.
States: Pending, Fulfilled, Rejected. And can be RESOLVED only once.  

Fetch function returns a Promise by default. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/5def2e39-14e9-4433-8d75-b0155b14dfe0)



![image](https://github.com/Gayathri229/JavaScript/assets/60467364/0c08c015-cd2a-42f7-b708-aa756a550967)


Definitions:  
Promise Object is a Placeholder for a certain amount of time until we receive a value from an asynchronous operation.
Container for a future value.  


MDN Definition [TO ANSWER IN INTERVIEWS]: Promise is an Object representing the Eventual Completion or Failure of an Async operation.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/893ec340-92ab-4154-a47f-2b403cdcfb02)


Callback Hell handling in Promise:

It is done through Promise chaining. 

This  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/6dca7740-06cc-42fe-a75b-bbd8f3bac6f1)

Equals  This. Promise chaining. Always don't forget to return the promise for the data to flow in Promise chaining. Else we might lose some data and the promise chain won't work as expected.  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/93f48e84-b0b6-4434-8bcb-bfc7906e6925)

With Arrow function, instead of normal function   
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/e4a1636a-a60c-4101-b126-616624ed513c)


HOMEWORK:  
What is a promise? A Promise is an Object which represents the eventual completion or failure of an async operation.  
  
Why promises are used? Promises help to overcome the challenges when using a Callback function i.e. callback hell and inversion of control. So, the promise guarantees us that it'll be definitely executed 100% of the time with either success or pending or failure and only once. This resolves Inversion of control. And to resolve callback hell we can use callback chaining using "then()" function by attaching callback functions to the promise object which will in turn return another promise object to its next callback function and so on.


  


Creating Promises:  
We can create a Promise using the Promise constructor. The Promise constructor takes a function with two arguments resolve and reject. These arguments are given by JavaScript by the design of Promise API.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/78fff741-400a-4417-87c4-a53014e65b38)

Promise creation in createOrder function:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/6fff0aff-44d4-42ce-835f-dc73574bbaf8)

Producing promise:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/a2afd384-b038-4489-8b82-b1a48425f15a)
  
Output: [for resolved promise]  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/8ab31980-326f-41d9-a349-e509503f593b)


We should always write a catch to handle the error if the promise gets rejected. catch() is also a method that is available with the Promise object to handle rejection errors.  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/55588ae1-7ee9-4dce-8831-16825ee39869)  
  
Output: when validateCart returned false  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/1cfc4dff-935a-4f56-a3ff-212167681b24)


Promise chaining:  
Here, we've returned the promise to the next chain, creating a promise chain. And this is how we pass the data in the promise chain. Here, the catch method at the end will handle any error caused in the whole promise chain BECAUSE it's placed at the end of the chain. 
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/8972ff35-9dcd-466f-93e9-962a47a817de)  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/c9a6c8a5-c617-4725-9a27-e0d0044f56cf)

Output:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/62381991-9d3e-442a-98eb-e99afea25230)


Let's say we have catch after the first then method, it'll handle only the error caused by the first then. The then methods placed after the catch will be called no matter what.  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/83831e1e-c502-4c72-ba96-e23d815f06e1)

So, in the above image, createOrder was set to false and catch was placed right after the first then, in the output we can see that cart is not valid is printed and still payment was successful is printed.
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/5e467e9a-266d-4adb-81af-94441423996a)


Just another example for catch at different places,  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/f4ed80d0-f631-46b9-9602-078367bef974)
