---
layout: default
title: Polymorphism
nav_order: 3
---
# Polymorphism
The word "polymorphism" means "many forms", and in programming it refers to methods/functions/operators with the same name that can be executed on many objects or classes.

## Polymorphism in functions
The `len()`  can be used on different objects :
``` python
>>> len('hello world') # length of string
11
>>> len([1,2,3,4]) # length of list
4
>>> len({'a':'apple', 'b':'ball', 'c':'cat'}) # length of dictionary
3
```
## class polymorphism

This code demonstrates the concept of inheritance and method overriding in Python classes. It shows how subclasses can override methods defined in their parent class to provide specific behavior while still inheriting other methods from the parent class.

```
class Bird:

	def intro(self):
		print("There are many types of birds.")

	def flight(self):
		print("Most of the birds can fly but some cannot.")

class sparrow(Bird):

	def flight(self):
		print("Sparrows can fly.")

class ostrich(Bird):

	def flight(self):
		print("Ostriches cannot fly.")

obj_bird = Bird()
obj_spr = sparrow()
obj_ost = ostrich()

obj_bird.intro()
obj_bird.flight()

obj_spr.intro()
obj_spr.flight()

obj_ost.intro()
obj_ost.flight()

```
output:

```
There are many types of birds.
Most of the birds can fly but some cannot.
There are many types of birds.
Sparrows can fly.
There are many types of birds.
Ostriches cannot fly.
```
### Further Reading

- [GFG - Polymorphism in Python](https://www.geeksforgeeks.org/polymorphism-in-python/)
- [w3 schools](https://www.w3schools.com/python/python_polymorphism.asp)