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


MAP:

We use Map in Arrays when we want to "transform" an array. Say we want to double/triple the values in the array.
Map takes function as an argument. Below example, converts each input in the array to its binary code. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/d23d99ce-4065-4562-95bb-df8b49798480)


FILTER:

Filter is used to filter out values from an array to obtain the required output. Below code filters out even values in the array. Function can be passed directly in the braces as well.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/4fdab352-f64f-4267-92c6-8e2612f5210a)



REDUCE:

Reduce is used in a place where we need to use the values in the array to arrive at a single value. Say we need to find out the sum of the elements or greater of all elements.
Here, we are finding the sum of elements. 
The function we pass for reduce takes two inputs such as "Accumulator" and "Current". Reduce function takes two inputs, one is the function, second is the initial values we need to pass for the accumulator variable.
In the findSum function, we have written the logic for finding the sum of the array. The same is implemented using reduce as well in the line acc = acc + curr where acc is initialized to 0 in the second argument of the reduce function.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/6c407f73-0eb0-4d98-a86b-af3e4252828f)

Example to find the max in an array
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/9fa15a41-25ff-4e93-8089-6509a953f499)


Example to find the number of people with same age. Here, we need to arrive at a single value i.e count of people with same age i.e use reduce here. 
For this, we have taken the accumulator to be an empty object. And if, acc does not have the object i.e say 26 since its the curr value, acc[26] is not present in the object we assign 1 to it denoting its first present. If acc[26] is already present we increment the value by 1.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/41cade15-a075-4fe7-9ade-287ecfff7d1c)



We can also chain map, filter and reduce. Let's take the below example. We want to print the first names of people with age less than 30. So first we filter using age and upon that result we use map to get the first names alone.
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/74a3b9f3-5756-4e27-ad8a-be8cb33e1a58)


Same example using reduce
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/b29a3eaa-a81e-4d0a-8029-1ec8a7592e48)

