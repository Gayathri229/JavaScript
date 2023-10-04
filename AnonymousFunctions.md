Function Statement / Function Declaration:
Function in the below image is a function statement. That's all. Nothing more nothing less.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/4d68ea39-1247-44b1-8977-a1514aaaf7ce)


Function Expression:

Assigning a function to a variable forms a function expression. Here functions are used as values.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/3dd8a246-4c13-468a-ac54-040210f08145)


Difference between Function Statement and Function Expression:

Hoisting plays a major role in these two. We can call the function a() before even defining it but same doesn't apply to b. During the memory  creation phase, a will be assigned with the function, but since b is declared as a variable it'll be assigned with "undefined" until the code hits the line where b is assigned with function and hence doesn't support hoisting.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/b1a5fa3a-de37-49a0-a665-fcd1699c4e8d)

Anonymous Function:
A function without a name. It doesn't have its own identity and results in a Syntax error as per ECMA script. Looks similar to a function statement but a function statement should have a name and hence results in error.

So then where are anonymous functions used?
Anonymous functions are used in a place where functions are used as values.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/3dd8a246-4c13-468a-ac54-040210f08145)


Named Function Expression:
We name a function and as well as assign it to a variable.
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/ae73b930-7a63-441d-916f-d1d37a00ecd8)

When we try to access this function as,
xyz() this throws an error because this is not created as a function in global scope. It is created as a local variable.

We can use this function inside this function itself but cannot use it outside like xyz() as it'll throw xyz is not defined error.
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/0419609c-78e3-4a6a-a6d2-73c1effde6aa)


Difference between parameters and arguments:

var b = function (param1, param2) {  ---> values passed here are called parameters and has local scope with the function. Can also be called as labels/identifiers
console.log("b called");
}

b(1,2); ----> values passed here are called arguments


First Class Functions:

We can pass a function as an argument to another function. We can also return a function from a function. We can treat a function as a value. This ability is called First Class Function. This can also be called as "First Class Citizens". Using let and const instead of var also acts the same here.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/18f5d05b-ee81-4146-99f0-265eb258885a)

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/bab67c78-b3a9-46f5-a762-a72828233ad9)

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/16f33bc9-ef64-4913-80bc-aaaa01de54ec)


