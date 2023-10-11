If we declare an array, say 
let arr = ["Akshay", "Aditya"];
when we type "arr.", we get access to length, push etc. This is because the as soon as you create an Object, Javascript Engine automatically attaches the object with some hidden properties and functions. This is due to prototype. It puts those properties and functions in an Object and attaches it to your object. Prototype is an Object that get attach to function/method/object and this object has some hidden properties.Whenever we create object/ function/ methods/ array/ variable , these all are attached with some hidden properties, which we call prototype.

You can see the same when you type say, "arr.__proto__."

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/31f78a8d-0a72-40a6-be93-597747631fbe)


![image](https://github.com/Gayathri229/JavaScript/assets/60467364/ad1c03e8-da5c-426f-9b2c-3bf64135a2cb)

arr.__proto__ prototype is same as prototype of Array i.e. "Array.prototype". arr.__proto__.__proto__ prototype is same as Object's prototype "Object.prototype". But Object's Prototype's prototype is null which is the end of chain. This is the prototype chain.
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/e99f6073-8c2d-4258-9a1a-7f14807a0dc6)

Below is the chain for function:
![image](https://github.com/Gayathri229/JavaScript/assets/60467364/2b11887b-d924-4e26-8dc0-f3b6354de133)

So, anything we create in Javascript, goes down the prototype chain and ends up being an Object. 

Prototypal Inheritance:
So here in the below example, because we have assigned object to object2's prototype, its checking if city is present in object2's prototype if not, goes to object's prototype and gets it which is its parent.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/4c603b94-047d-4a2a-aaaa-4a4aed209387)

When we try to access getIntro using object2, it prints "Aditya from Dehradun". This is because, "this" object is pointing to object2 and since it has name in it, it takes "Aditya", but since it doesnt have city in object2 proceeds to take it from object.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/c370f9a1-f613-4723-ac82-47095cd500f5)

So, object2 is inheriting properties and methods from object / object's __proto__. 


Another concept is that, we can use mybind() as used in below example, here we've attached the function to Function prototype itself, so now any function we write will have mybind() in its prototype properties and we can use it like fun.mybind(), fun2.mybind() for any function.

![image](https://github.com/Gayathri229/JavaScript/assets/60467364/0cc4eb69-df49-464d-bf54-986f7745a843)
