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

- The identity can be considered as the name of the dog.
- State or Attributes can be considered as the breed, age, or color of the dog.
- The behavior can be considered as to whether the dog is eating or sleeping.


## Builtin types in python
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
[functions are also objects](Code/Objects/function_object.py)


These are called builtin types and function differently from other objects.



## Init method in ptyhon 

- Similar to constructors in [Java](https://www.geeksforgeeks.org/constructors-in-java/) and [C++](https://www.geeksforgeeks.org/constructors-c/).

### What is self in class ?

When we create an object for the class and call the function, the self is replaced with the created object. It is like a placeholder for the object. In the class we created, we have two variables common to all the objects we create. Hence, even if we called the variables with the object name, we will get the same values for all the objects.

### What `'__init__'` can do ?
1. Every object could have its values for the attributes of a class. This functionality can be acheived using the `__init__` method.
2. It is a constructor, allowing class to hold objects with different values.
3. We need not call it like we call a normal method. It is similar to a method inside a class. It is executed as soon as an object is created for the class.

``` python
class planet:  
    def __init__ (self, name, number):  
        self. name = name  
        self. number = number  
    def function (self):  
        print ("I am", self. name)  
        print ("I am the", self. number, "planet in the solar system")  
          
earth = planet ('earth', 3)  
earth. function ()  

```
![output](https://static.javatpoint.com/python/images/__init__-in-python2.png)
[source](https://www.javatpoint.com/__init__-in-python)

## Modifying Attributes

Consider the previous example: 
``` python
class planet:  
    def __init__ (self, name, number):  
        self. name = name  
        self. number = number  
    def function (self):  
        print ("I am", self. name)  
        print ("I am the", self. number, "planet in the solar system")  
          
earth = planet ('earth', 3)  
earth. function ()  

```
here we can create methods which modify the attributes `name` and `number` called `set_name` and `set_number` to get these attributes we use `get_name` and `get_number` methods respectively.
``` python
class planet:  
    def __init__ (self, name, number):  
        self. name = name  
        self. number = number 
     
    def function (self):  
        print ("I am", self. name)  
        print ("I am the", self. number, "planet in the solar system")  

    def set_name(self, name):
        self.name = name

    def set_number(self, number):
        self.number = number
    
    def get_name(self):
        return name
    
    def get_number(self):
        return number


earth = planet ('earth', 3)  
earth. function ()  

```
This is similar to [getter and setter method in java](https://www.w3schools.com/java/java_encapsulation.asp). For more on this refer the Encapsulation section.

## Interaction between classes

Consider the follwing code which demonstrates a student to course relationship.

``` python
class Student:
    def __init__(self, name, age, grade):
        self.name = name
        self.age = age
        self.grade = grade
    
    def get_grade(self):
        return self.grade

class Course:
    def __init__(self, name, max_students):
        self.name = name
        self.max_students = max_students
        self.students = [] 
    
    def add_student(self, student):
        if len(self.students) < self.max_students:
            self.students.append(student)
            return True
        else:
            return False
    
    def get_avg_grade(self):
        value = 0
        for student in self.students:
            value += student.get_grade()
        return value / len(self.students)

s1 = Student('Tim', 19, 95)
s2 = Student('Bill', 19, 75)
s3 = Student('Jill', 19, 65)

course = Course("Science", 2)
course.add_student(s1)
course.add_student(s2)
print(course.students[0].name)
print(course.get_avg_grade())
```