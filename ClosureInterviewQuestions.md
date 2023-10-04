Question 1:

Lets take the below example for setTimeout, we have printed i in timeout function with wait time 3s and printed Namaste javascript outside of setTimeout.
Here, it doesn't wait for 3s for i to get printed and then print Namaste Javascript. What happens in the back is, setTimeout takes the callback function and stores it, attaches the timer, when the timer expires the function is called. A closure is formed and it has access to reference of i, so the function is stored along with the timer and when the timer expires the function is put on the call stack and the function is executed.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/95b881af-6624-44c1-be27-8607790e1b68)



Question 2:

Let's say we want to print 1 after 1000ms, 2 after 2000ms, 3 after 3000ms, 4 after 4000ms, 5 after 5000ms. We write the below code using for loop.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/05cfa56a-d3d0-4e95-add0-2a8e27df751b)

But the output of this function will be, 6 after 1s, 6 after 2s and so on.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/3af4d0a5-93ed-4b6b-be0e-27de4a2b95e8)

This is because, the function is first run in loop and stored with the timer. So i gets incremented till 6 here. When the timer expires, each function is run again and the reference of i then is printed which is 6. So this means, every copy of the function is referring to the same reference of i. 

So, we can fix this by changing the "var" declaration of i to "let" declaration. Since let has block scope, each time the function is run, it points to the new copy/reference of i. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/9d23bf0d-c159-4748-b681-c1ef1eef25ae)


We can also fix this by using "var" declaration itself, that is by introducing a function to enclose the timeout. Take a look at the below image. Since this introduces block scope, each time the function is called, due to closure the value of i will be remembered for that instance and will be printed as expected.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/8dd308ba-95b9-4625-b820-d573dafae423)

Use of double paranthesis:

Calling outer()(), means calling the function inside outer here. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/9172fd62-d885-40fa-b9e6-424cdfe60944)

We can also do the above like the below image, both are same.
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/7e2f6ca6-e8c3-41dd-bd4a-72067ee68a84)


Data Privacy using closures and separate closure concept:
Here in counter() function, we have count variable which can only be used/incremented by calling the counter function and not otherwise.

Another concept here is, we have called counter() and assigned it to counter1, now this would've formed a closure. When we try calling counter again as we've done in code and assigned it to counter2, this will form a separate closure with its own separate count variable. And this is why, when we print count value each time, it starts from 0 for both counter1 and counter2.


function counter() {
   var count=0;
   return function incrementCounter() {
      count++;
      console.log(count);
   }
}

var counter1 = counter();
counter1();
counter1();

var counter2 = counter();
counter1();
counter1();
counter1();



This will work the same, even when we redeclare counter1 and call counter function or simply reassign counter function to counter1 itself.

Use of double paranthesis:

Calling outer()(), means calling the function inside outer here. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/9172fd62-d885-40fa-b9e6-424cdfe60944)

We can also do the above like the below image, both are same.
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/7e2f6ca6-e8c3-41dd-bd4a-72067ee68a84)


Data Privacy using closures and separate closure concept:
Here in counter() function, we have count variable which can only be used/incremented by calling the counter function and not otherwise.

Another concept here is, we have called counter() and assigned it to counter1, now this would've formed a closure. When we try calling counter again as we've done in code and assigned it to counter2, this will form a separate closure with its own separate count variable. And this is why, when we print count value each time, it starts from 0 for both counter1 and counter2.


function counter() {
   var count=0;
   return function incrementCounter() {
      count++;
      console.log(count);
   }
}

var counter1 = counter();
counter1();
counter1();

var counter2 = counter();
counter1();
counter1();
counter1();


This will work the same, even when we redeclare counter1 and call counter function or simply reassign counter function to counter1 itself like below image.

![Screenshot 2023-10-04 112624](https://github.com/Gayathri229/JavaScript/assets/60467364/067aadfe-073a-4b86-9f0e-114e92ca70ab)

