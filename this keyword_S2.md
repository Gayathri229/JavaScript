// global space  
this => globalObject (window)  
Note: this always refers to a globalObject. Be it a browser/node js/native app etc. In browsers, this globalObject is WINDOW.  
In nodeJS, its global.  

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/e019a8e2-ad7f-48af-bd76-5606a5ccec81)
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/461b4436-0a6b-43b6-a38f-cf5016ba5350)


// inside a function  
-> strict mode:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/7785a0d1-6248-46e5-81a4-6f646c906e7f)
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/68654b36-a3e5-4e8c-8c3c-44dac6f978ab)

-> non-strict mode:  
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/fa177e27-6f37-4665-8209-bd743dd42646)
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/f112c22b-6469-413b-b002-33242964667f)

So, by default value of this keyword inside function is "UNDEFINED"


this keyword value depends on how the function is called as well
Note: strict mode in screenshot
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/7d6ffbfa-9e6b-4505-be0d-521696935611)
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/b790c033-a198-47a5-8097-0895545f91f5)


