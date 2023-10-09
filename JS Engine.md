JavaScript Run time environment:

JS run time environment has all the elements required to run JS. JS Engine is the heart of JS run time environment.
![Screenshot 2023-10-06 184214](https://github.com/Gayathri229/JavaScript/assets/60467364/f7caddf0-9203-4e6d-9566-9eb4ad947783)

Browser is able to run the JS code because it has JS run time environment. Every browser has its own JS engine. 
JS Engine is nothing but a code written in low-level language. It takes the high level code written by us and gives the machine level code which can be executed by the machine. Google's V8 Engine is written in C++.
We can create our own JS engine. The protocol is that it should follow the ECMAScript standards. 

First JS Engine was developed by the creator of JS called SpyderMonkey.


JS Engine Architecture:

These are the changes, the code undergoes

![Screenshot 2023-10-06 185605](https://github.com/Gayathri229/JavaScript/assets/60467364/f67bc1bb-343d-4173-a8e2-ddc9813988a8)


PARSING:

Code is broken down into tokens. Eg: let a = 7;
Here, let is a token, a is a token, = is a token, 7 is a token.

Syntax Parser: Converts the code into Abstract Syntax Tree. It looks like the below image for the code written on the left in the image. This AST is sent to the compilation phase.

![Screenshot 2023-10-06 190116](https://github.com/Gayathri229/JavaScript/assets/60467364/87d4c581-55f1-428c-ac3c-e830bc3a04f6)


COMPILATION:

Interpreter: Executes the code line by line in the given order. It doesn't know what will happen in the next line.
Advantages: Code execution is fast. Doesn't have to wait for the code to get compiled.

Compiler: Code is first compiled before executing. After compilation, we get an optimized version of the code which is then executed.
Advantage: Code is more efficient.

Is JavaScript Interpreted or Compiled Language?

It depends on the JS Engine. Modern compilers use a combination of both Interpreter and Compiler which makes it a Just In Time Compilation [JIT Compilation]. Engines use Interpreter along with the Compiler.


So, here compilation and execution goes hand in hand.
The Abstract Syntax Tree is sent to the Interpreter which converts high level into Byte Code and the code moves to the execution step. While the code is interpreted line by line it takes the help of compiler to optimize the code. This happens on run time. This interpretation and compilation can happen in multiple phases. Since this compilation happens on run time it is called Just In Time compilation. All the JS engines have their own algorithms of doing this.

In some JS engines we have something called AOT.
Ahead Of Time compilation - It takes a piece of code which is going to be executed later and optimizes it as much as it can. This also produces the byte code which goes to the execution phase. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/7e0c5eb1-96e5-4555-bca7-d3ccbd8895ed)

EXECUTION:
Execution is not possible with Memory heap and Call stack[these are present in JS Engine]. Memory heap is a place where all the memory is stored. It is constantly in sync with the call stack, garbage collector, etc. Memory heap is the place where all the functions and variables are assigned memory.

Garbage Collector:
It uses the algorithm called Mark and Sweep algorithm. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/bd4b1c3d-7e59-4eab-857d-46e1beb1a6a5)


There are other forms of optimization that the compiler does like inlining, inline caching, copy elision etc. 

Google's V8 JS engine is the fastest till now. V8's Interpreter is called Ignition. V8's Optimizing Compiler is called Turbo Fan. V8's Garbage collector - Orinoco. 

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/0e8533d3-b565-4c72-bb2d-34e8685663e0)
