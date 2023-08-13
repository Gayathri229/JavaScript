Hoisting in JavaScript

Lets take the below code for example:

<img width="463" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/e18f1208-9048-4f6e-9e66-e69794a2f658">

Here, we have called the function before it was defined and we have printed the value before it was initialized.

But the output here will be, 
<img width="274" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/a3d1f742-a3c9-419b-91a5-28b0969f71e5">
This is because, when the code is executed, memory is first allocated for all variables and functions. Variables will be assigned as undefined and functions will be assigned with the whole code.
So when we printed "x" it was undefined at that instance.

For this code,

<img width="430" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/84cd0b62-a8f8-45a1-9678-a3d53c938f4a">

The output will be

<img width="571" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/c2e35fb8-b17c-4f8f-90a2-5446a34c2275">

Hoisting in JavaScript allows us to access variables and functions even before we've initialized it without any error.

