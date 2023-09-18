Lexical environment
Wherever execution context is created, a lexical environment is created. Lexical environment is the local memory along with the reference to lexical environment of its parent.
Lexical parent means where the function actually sits in the code.

![Screenshot 2023-09-18 152001](https://github.com/Gayathri229/JavaScript/assets/60467364/c974b743-754b-457e-9f0a-296fca1433a3)

Lexical means hierarchy/in sequence. In the above code, c() is lexically inside a().
a() is lexically inside the global scope.

Let's see how the lexical environment is with the below example,

![Screenshot 2023-09-18 160527](https://github.com/Gayathri229/JavaScript/assets/60467364/afca09d1-d4cc-4a53-b2d3-7ebe6f9dd891)

Here the orange box represents the lexical environment, so the c() gets access to its variables/functions and the lexical environment of its parent i.e a().

a() gets access to its variables and the lexical environment of its parent ie global execution context.

Global execution context has access to its variables/functions and lexical environment of its parent which is NULL.

![Screenshot 2023-09-18 160948](https://github.com/Gayathri229/JavaScript/assets/60467364/6908f0cc-792a-459a-9cc3-710fafd81994)



Now when we try to console log b inside c(), it tries to find b inside local memoery of c(). So it goes to the lexical environment of its parent i.e a()[where the acutal code and values are present] 
and searches for b there. Finds b there and prints it in the console.

If b was not present in a(), it would'e gone to lexical env of a() parent i.e global context, doesn't find there and again moves to global execution context's lexical environment which is pointing to NULL, so now
JS engine throws the error "not defined".

This way of finding the variable or anything i.e searching in local memory then moving to its parents lexical environment. This is known as Scope Chain.

Now let's see the same example running in a browser,

This screenshot represents the lexical environment of global execution context, here we can see the local memory of Global execution context,

![Screenshot 2023-09-18 184901](https://github.com/Gayathri229/JavaScript/assets/60467364/824d291b-9cfc-4553-9d5d-9f4fcdad945b)

This below image represents the lexical environment of a(), here we can see the local memory of a() and lexical env of its parent [Global exe context]

![Screenshot 2023-09-18 184928](https://github.com/Gayathri229/JavaScript/assets/60467364/40ace54a-6a4a-4835-ada3-fa5ec3499f0e)

This below image represents the lexical environment of c(), here we can see the local memory of c() and lexical env of a() and lexical env of its parent [Global exe context]

![Screenshot 2023-09-18 184940](https://github.com/Gayathri229/JavaScript/assets/60467364/40bcd299-15c6-4f51-bc74-11750ac18de3)






