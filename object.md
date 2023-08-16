---
layout: default
title: Object
nav_order: 1
---
# Object 
The object is an entity that has a state and behavior associated with it. It may be any real-world object like a mouse, keyboard, chair, table, pen, etc. Integers, strings, floating-point numbers, even arrays, and dictionaries, are all objects. More specifically, any single integer or any single string is an object. The number 12 is an object, the string “Hello, world” is an object, a list is an object that can hold other objects, and so on. You’ve been using objects all along and may not even realize it.

An object consists of:

- State: It is represented by the attributes of an object. It also reflects the properties of an object.
- Behavior: It is represented by the methods of an object. It also reflects the response of an object to other objects.
- Identity: It gives a unique name to an object and enables one object to interact with other objects.


To understand the state, behavior, and identity let us take the example of the class dog. 
``` python
class Dog:
    pass
```

The identity can be considered as the name of the dog.
State or Attributes can be considered as the breed, age, or color of the dog.
The behavior can be considered as to whether the dog is eating or sleeping.

In python we come accross a lot of objects without knowing them a lot of the common data types like `int`, `str` and all are objects here is a simple experiment to find out 
``` python
>>> type('hello world')
<class 'str'>
>>> x = 5
>>> type(x)
<class 'int'>
>>> y = 5.667
>>> type(y)   
<class 'float'>
```
[functions are also objects](/Objects/function_object.py)
