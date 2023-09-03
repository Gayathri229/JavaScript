Shortest program in Javascript

It's nothing but an empty js file. If we try running the file, a Global Execution Context is created and memory space is set up.

Javascript engine also creates a Window. If we see in the below screenshot, the object window has a lot of variables and functions in it and it is created in the global space which is done by the Javascript engine. These variables and functions can be used anywhere in the program.

<img width="1512" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/8a884321-cd03-4c79-99a5-8aeb2b321e9f">


The Javascript engine also creates "this" keyword. At the global level, this points to the window object. 
<img width="1512" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/e2c61d8f-5fb8-435e-af15-29a4e08413e3">

What is a window object?

Window is a global object which is created along with the Global Execution context. Along with this, "this" variable is created. All the Javascript engines have the responsibility to create Global object. In browser, it is knowm as Window. In case of Node it is called something else and so on.

Note: 
Each web browser typically has its own JavaScript engine. For example, Google Chrome uses the V8 engine, Mozilla Firefox uses SpiderMonkey, and Microsoft Edge uses Chakra or V8, depending on the version.


In Global Execution context, this is equal to Global Object.

<img width="361" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/5151fb10-a164-45d2-bc81-e7c9f4226734">

So whenever a execution context is created, "this" is created along with it i.e for both global and functional execution context.

What is a Global space?

It is nothing but any code we write except for any variable / function "inside any function". Or Anything which is not inside a function is Global space.

Let's take the below example:

<img width="157" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/33a562f3-dc62-42e3-a4f0-e77640e75898">

Variables and Objects get attached to the Global object. Refer the below screenshot for reference. Here we can see the variable a and function b() but x won't be present here. 

<img width="590" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/b445ab4f-f7aa-4522-9d47-e3415ffd7216">

To access these variables, we can write

console.log(window.a); 
OR
console.log(this.a);
OR
console.log(a);

If we don't mention anything before the variable it automatically considers the Global space. Here if we try to access variable x, it searches in the Global space/ Global Object and throws "not defined error".

<img width="932" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/a7159200-3061-47cd-83a4-17db5ff9b290">






