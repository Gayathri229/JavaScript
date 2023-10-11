Higher Order Function:

A function which takes another function as an argument or returns a function is known as Higher Order Function.

In this example, y() is the higher order function. And x() is the callback functions.
Eg: ![image](https://github.com/Gayathri229/JavaScript/assets/60467364/7664e9ab-5a98-4c72-a852-ba1b3ead9deb)


Functional Programming:
Let's say we need to print the area, circumference and diameter of circle given the radius in an array. We write 3 separate functions to do this respectively. But we can see that 90% of the code is same except for the logic. So, we need to follow the rule, DRY Don't repeat yourself and keep the code optimized. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/fba091c9-3d71-42cf-90fd-81510739893c)

For this we can have one single function to calculate the logic we want, and separate the logic part into 3 different functions for calculating area, circumference and diameter. As given in the below image, we pass radius and the what we want to calculate, and from within that function we call the respective area/cicrum/diameter function which gives the same results as before. Here, every unit of function has its own unique function/job and can be reused. Likewise, always break the logic into small parts.
Also here calculate is the higher-order function and the logic is the callback function.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/282b70af-def4-413e-b5e3-e8c9d9b51b47)

The calculate function in the above example, is similar to map function. Line number 23, gives the same output as calculate function. So, we've written our own implementation of map. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/53725384-7ae5-464e-bf6c-048e2412f3ba)

Just for the sake to make it similar to map function, we are making few more changes to the calculate function and add it to the Array prototype. So now, this calculate function will be available as a property to all/any array we declare. Here, we can replace the "array[i]" in calculate function to "this" keyword as the array with which we call the function gets passed there.

For my understanding: Once we've added the calculate function to Array prototype, it has become a method like length/push() so we pass the argument to it which is the "logic" here and the array with which we call becomes its current instance and so don't need to specify as arr anymore and that's why "this" keyword came in here.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/fedbcf87-f3f9-4e5d-a9c3-74d221cadd1e)


MAP, FILTER AND REDUCE:

We use Map in Arrays when we want to "transform" an array. Say we want to double/triple the values in the array.
Map takes function as an argument. Below example, converts each input in the array to its binary code. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/d23d99ce-4065-4562-95bb-df8b49798480)
