<img width="491" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/d30ba60e-cc3a-464e-b0a9-bc5ee9582b3d">

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

This is because, x is not initialized at all, so when the code is executed it won't be allocated any memory in the first place. So when we tried to print the value, it searches in the memory and says it couldn't find any variable called x i.e "x is not defined" error is thrown.

Hoisting in JavaScript allows us to access variables and functions even before we've initialized it without any error.

When we try printing a function without calling it like in the below example line no 5, the whole function gets printed in the console.

<img width="405" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/81bdd8d8-960c-41e1-9334-3c838597c368">



Arrow functions:


<img width="491" alt="image" src="https://github.com/Gayathri229/JavaScript/assets/60467364/adc21182-bf39-483e-9486-3676dc76f498">

Eg:
var getName = () => {
console.log("Namaste JavaScript");
}

Here this function gets treated like a variable and will be assigned with undefined in the memory allocation phase. 



We can also define functions like below. Here also this function gets treated like a variable.

var getName2 = function() {

}

