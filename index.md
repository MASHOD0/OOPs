---
title: Home
layout: home
---

# Guide-to-object-oriented-programing
## Introduction
**Object Oriented Programming (OOPs)** is a programming paradigm which uses [objects](https://en.wikipedia.org/wiki/Object_(computer_science)) and [classes](https://www.w3schools.com/python/python_classes.asp). The following are the core concepts behind OOPs.
1. Abstraction
2. Encapsulation
3. Polymorphism
4. Inheritance
5. Association
6. Composition
7. Aggregation
## Object 
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

These are called builtin types and function differently from other objects.

## Methods

## Abstraction
## Encapsulation
## Polymorphism
## Inheritance
### Association
### Composition
### Aggregation

## Recommended Reads and videos
- [OOP In Python GFG](https://www.geeksforgeeks.org/python-oops-concepts/)
- [OOP In 7 Minutes - Programming with Mosh](https://www.youtube.com/watch?v=PFmuCDHHpwk&pp=ygUZcHJvZ3JhbWluZyB3aXRoIG1vc2ggb29wcw%3D%3D)
- [Python classes and objects - Socratica ](https://www.youtube.com/watch?v=apACNr7DC_s&pp=ygUZcHJvZ3JhbWluZyB3aXRoIG1vc2ggb29wcw%3D%3D)
- [Python Object Oriented Programming for Beginners - Tech With Tim](https://www.youtube.com/watch?v=JeznW_7DlB0&t=659s&pp=ygUZcHJvZ3JhbWluZyB3aXRoIG1vc2ggb29wcw%3D%3D )
### Not Completely Related but must go through
- [SOLID PRINCIPLES IN PYTHON](https://www.youtube.com/watch?v=pTB30aXS77U&pp=ygUQYXJqYW4gY29kZXMgb29wcw%3D%3D)
- [SOLID Relavence](https://blog.cleancoder.com/uncle-bob/2020/10/18/Solid-Relevance.html)

