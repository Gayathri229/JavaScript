// global space
this => globalObject (window)
Note: this always refers to a globalObject. Be it a browser/node js/native app etc. In browsers, this globalObject is WINDOW.
In nodeJS, its global.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/e019a8e2-ad7f-48af-bd76-5606a5ccec81)
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/461b4436-0a6b-43b6-a38f-cf5016ba5350)


// inside a function
-> strict mode:
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/c0fe9e0e-9f5c-4f57-88e2-03c232df4382)
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/68654b36-a3e5-4e8c-8c3c-44dac6f978ab)

-> non-strict mode:
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/f0af376b-6e2f-4247-a3c2-17e07e27a429)
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/f112c22b-6469-413b-b002-33242964667f)

So, by default value of this keyword inside function is "UNDEFINED"

