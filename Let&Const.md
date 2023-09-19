Let and const declarations are hoisted

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



