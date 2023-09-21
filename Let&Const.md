![image](https://github.com/Gayathri229/JavaScript/assets/60467364/f1b867f2-63a3-4dec-a126-a80d36f0189b)Let and const declarations are hoisted

When we try to access a "let" variable after initializing but before declaring a value, it throws "Reference error, Cannot access before initialization."

![Screenshot 2023-09-19 114011](https://github.com/Gayathri229/JavaScript/assets/60467364/39afad87-960b-4ff5-8d31-3dd626d141d2)


Let's see what happens in the background,
let and var are stored in a different memory space. Var is attached to the global scope whereas we can see let under something called "script". We cannot access the let and const values before assigning them 
with some values. This is what is called hoisting for let and const.

![Screenshot 2023-09-19 114216](https://github.com/Gayathri229/JavaScript/assets/60467364/8368c2c2-e11e-48de-8f28-c4c0c0f4d44b)


Temporal dead zone:
It the time since the let variable was hoisted/declared and till its assigned a value/initialized.

When we try to access a variable in a temporal dead zone, it throws ReferenceError, Cannot access before initialization.



Window object -> same as global object
Var variables are attached to window object. Let and Const are not attached to window object. They are stored in a different space. 

We cannot redeclare let declarations. JS Engine throws a Syntax error.
Let can be initialized first and then declared anywhere in the program. But this cannot be done with const variable. Syntax error will be thrown.

![Screenshot 2023-09-19 120422](https://github.com/Gayathri229/JavaScript/assets/60467364/cd385a6a-9fc3-496c-9c4f-4f785b832ab6)


When we try to reassign a const variable, typeError is thrown. 
![Screenshot 2023-09-19 120642](https://github.com/Gayathri229/JavaScript/assets/60467364/b518f58b-a517-416c-ad75-f5ace887e7f5)





TypeError: Assignment to a constant variable -> When we are trying to declare a const variable separately or again after initializing it.
SyntaxError: Missing initializer in const declaration -> When we haven't declared any value to const variable.
SyntaxError: Identifier has already been declared -> When we try to redeclare a let variable again.
ReferenceError:  -> When javacript engine tried to find a variable in the memory space and cannot access it.
ReferenceError: Cannot access before initialization -> When we try to access a let variable before initializing it with a value i.e when it is in the temporal dead zone.
ReferenceError: y is not defined -> when a variable is not present in the memory i.e we don't have such a variable in code.


Preference of Usage:
1. Const
2. let
3. var

How to avoid temporal dead zone?
Always have the declaration and initialization part at the top of the code. When the code runs, it hits the initialization and declaration part first and then runs into the logic. This also means we shrink our 
temporal dead zone to 0.



Scope of Let and Const:
Let and const are block scoped.
A block is defined by {}. It is also known as compound statement. 

We use blocks where JavaScript expects a single statement. Let's see the below example:

if(true) -> here after the if condition, JS expects a single statement under the if condition, but we use {} to write multiple statements. Here {} is a block.


Block scope: [Block scope is different from function scope. Block scope: any block such as if/for/while loop. Function scope when a variable declared inside a function will not be visible outside the function.] 
What all variables and functions we can access inside this block. 

Here in the below image, we can see that b and c are stored in a different space that is reserved for the block. a is stored in global scope.
Once the block is executed, let and const are no longer accessible but var can be accessed.
![Screenshot 2023-09-19 185651](https://github.com/Gayathri229/JavaScript/assets/60467364/07546aa3-d88e-4857-84f4-58b93035b9ac)

We can see that once the block is executed, the block scope is removed in the background.

![Screenshot 2023-09-19 190516](https://github.com/Gayathri229/JavaScript/assets/60467364/45d46cb0-4857-46fe-938a-640309b9dc5c)


Shadowing in JS:

Let's take the below code for example, var a is assigned with 100 outside the block, the same var a is assigned with 10 inside the block, here the "a" inside the block is shadowing the "a" outside the block.
Since var a is present in global scope, when we assign it with different value, it gets changed to the secondly assigned value.

![Screenshot 2023-09-19 190920](https://github.com/Gayathri229/JavaScript/assets/60467364/ea79c26e-ded2-496c-bd9a-0b586efd7b61)


Let's take the below example for let declaration,

Here since let is block scoped, value of b is 100 outside the block and 20 inside the block. So b=20 is shadowing b=100. We can also see that, value 20 is in block scope in console and 100 is in a different scope [under script dropdown].

![Screenshot 2023-09-19 191758](https://github.com/Gayathri229/JavaScript/assets/60467364/a9ad3fd9-6366-464c-8401-4292c28d783b)

Same happens for const as well here, value of c inside the block is 30 and outside the block is 100. c=30 shadows c=100.



Illegal shadowing:

We can shadow a var using a var in a block, a let using a let in a block, but not a let using a var in a block as shown in the below example. 

![Screenshot 2023-09-19 214024](https://github.com/Gayathri229/JavaScript/assets/60467364/a8d9bb23-dd61-4b03-89f3-640050aaa0fa)

Shadowing var using let in another block is also allowed but not the vice versa.

![Screenshot 2023-09-21 080331](https://github.com/Gayathri229/JavaScript/assets/60467364/074c812d-0d1e-4ad7-848b-7a20ce5ee1cc)

Let's go deep into this illegal shadowing, if we try to shadow let using var, we should not cross the boundaries/scope of let, this means let cannot be redeclared, so when we do that using var, error is thrown. 

![Screenshot 2023-09-21 080600](https://github.com/Gayathri229/JavaScript/assets/60467364/cf840c63-3d73-4efa-8e7f-459463cf7943)

But if we use the same var a inside a function, like in below image, it doesn't throw error as it doesn't interfere with the scope of let outside the function.

![Screenshot 2023-09-21 080854](https://github.com/Gayathri229/JavaScript/assets/60467364/9a345718-578b-4fa7-9f30-0c6f3634d52b)


Lexical scope:

Block scope also follows lexical scope. In the below example, it has taken the nearest value to console.log and printed 200.

![Screenshot 2023-09-21 081949](https://github.com/Gayathri229/JavaScript/assets/60467364/3e01cdff-0d07-400b-8fcd-23ee7f1fe549)

And when we try to print it like the below example, it has printed 100.

![Screenshot 2023-09-21 082106](https://github.com/Gayathri229/JavaScript/assets/60467364/9b6e46cf-416b-4852-b2fb-29be91b08027)

Here, we can see there a block scopes for each time we declared a, a script and a global scope. 

![Screenshot 2023-09-21 082533](https://github.com/Gayathri229/JavaScript/assets/60467364/868bfab6-d064-406d-9cb1-5622b9280bfc)


Here, when we removed a=200 in the 3rd block and printed the value, it has printed 100. This shows it is following lexical scope chain in a block as well i.e has access to other blocks/outside blocks as well.

![Screenshot 2023-09-21 083334](https://github.com/Gayathri229/JavaScript/assets/60467364/30135ec8-95c2-4d00-9b49-8189eaf6b343)



Scope in function and arrow function:

They work the same for both function and arrow function.
