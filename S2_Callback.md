Callback functions help to handle async operations in JS. 

Let's say we are placing an order in an e-commerce website. So it goes like this, we add items to the cart, proceed to payment, show the order summary to us, and deduct the amount from the wallet.  
But we don't know how much time will it take for the user to proceed to payment from cart, since time is unknown for proceed payment, order summary and deducting wallet time is also unknown.  
So, we put these in callback methods. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/628f6599-c2df-43e2-9994-e7508a3a07c7)

Here, we can see there is a callback function inside another callback function, and so on(nested callbacks). This is called Callback hell.  
This structure is called the Pyramid of Doom.  

Also, now it is the job of createOrder to call the proceed to payment and this chain continues to all callback methods i.e. proceed to payment is responsible for calling show summary, show summary is responsible for calling update wallet amount. This means the control of code is given to createOrder API. [Inversion of control]


Inversion of Control:  
As mentioned previously, when we lose control of our code when using callbacks we never know if the piece of code gets executed or not, or whether will it get executed properly without any errors/bugs. 






Promises are used to handle async operations in JavaScript.
