Closure:

A function bind/bundled together with its lexical environment / Function along with its lexical scope.

Here, we can see, "Closure(x)" under scope which means y() has access to variables of x which forms a closure.

![Screenshot 2023-09-21 113624](https://github.com/Gayathri229/JavaScript/assets/60467364/d9740056-d55c-4977-b4ca-7b74f5774a72)


In JS, we can assign a function to a variable
![Screenshot 2023-09-21 113854](https://github.com/Gayathri229/JavaScript/assets/60467364/0872a720-a8d6-4e7a-bb72-ed2134f3fba6)


We can pass a function as a parameter to another function
![Screenshot 2023-09-21 113905](https://github.com/Gayathri229/JavaScript/assets/60467364/ae27645b-994f-4c0d-bc77-4a8439d1a547)

We can return a function from a function. Here the whole function y will get printed when we try printing it.
![Screenshot 2023-09-21 114035](https://github.com/Gayathri229/JavaScript/assets/60467364/2aaed320-462e-495f-b21e-e710b8cecafc)


Let's take another example for CLOSURE, here we have returned y() inside x() and stored it in z. y() will have access to its lexical parent env which is x(). Now, in the background, the execution context of x() would have been deleted once x got executed. Now, z has a reference of y(). When we call z(), even though it is not inside x() anymore, it remembers its lexical scope and prints the value of a i.e 7. This is because of closure. 

![Screenshot 2023-09-21 115913](https://github.com/Gayathri229/JavaScript/assets/60467364/1dc0e606-2bc6-4631-9073-0a0a197026e2)

We can also write, return y in the above example as ->
![Screenshot 2023-09-21 121220](https://github.com/Gayathri229/JavaScript/assets/60467364/c31b5831-7b8e-471a-a3ec-02bba0d50884)


CLOSURE CORNER CASES:
In the below example, a is updated to 100 before returning y, and the output also prints 100, this is because it refers to the reference to a and not to just value of a. This way, now a has the value 100 so output is 100.
![Screenshot 2023-09-21 122429](https://github.com/Gayathri229/JavaScript/assets/60467364/0a820724-e994-4490-be9d-a0568ff92a5a)


Now let's go one more level deep into closure, in the below example we are placing the example code mentioned in the above scenarios in another function, closure will work then as well i.e in the second image we can see that, it has the closure of x and z(parent's parent) when the debugger is in function y(). 

![Screenshot 2023-09-21 161224](https://github.com/Gayathri229/JavaScript/assets/60467364/04768257-1b79-4bc9-babe-7decec3fa700)

![Screenshot 2023-09-21 161232](https://github.com/Gayathri229/JavaScript/assets/60467364/c637853c-1995-4642-822c-fedae84bb3ae)



USES OF CLOSURE:

![Screenshot 2023-09-21 161827](https://github.com/Gayathri229/JavaScript/assets/60467364/857bba06-f3fb-4541-a35c-4af2d6204a6d)

