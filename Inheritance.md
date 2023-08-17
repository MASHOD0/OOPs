---
layout: default
title: Inheritance
nav_order: 5
---
# Inheritance

Inheritance is the capability of one class to derive or inherit the properties from another class. The class that derives properties is called the derived class or child class and the class from which the properties are being derived is called the base class or parent class. The benefits of inheritance are:

- It represents real-world relationships well.
- It provides the reusability of a code. We don’t have to write the same code again and again. Also, it allows us to add more features to a class without modifying it.
- It is transitive in nature, which means that if class B inherits from another class A, then all the subclasses of B would automatically inherit from class A.
### Types of Inheritance
- Single Inheritance: Single-level inheritance enables a derived class to inherit characteristics from a single-parent class.
- Multilevel Inheritance: Multi-level inheritance enables a derived class to inherit properties from an immediate parent class which in turn inherits properties from his parent class. 
- Hierarchical Inheritance: Hierarchical-level inheritance enables more than one derived class to inherit properties from a parent class.
- Multiple Inheritance: Multiple-level inheritance enables one derived class to inherit properties from more than one base class.
### Inheritance in Python

``` python
"""Python code to demonstrate how parent constructors are called."""

""" parent class """
class Person(object):

	# __init__ is known as the constructor
	def __init__(self, name, idnumber):
		self.name = name
		self.idnumber = idnumber

	def display(self):
		print(self.name)
		print(self.idnumber)
		
	def details(self):
		print("My name is {}".format(self.name))
		print("IdNumber: {}".format(self.idnumber))

"""child class"""
class Employee(Person):
	def __init__(self, name, idnumber, salary, post):
		self.salary = salary
		self.post = post

		# invoking the __init__ of the parent class
		Person.__init__(self, name, idnumber)
		
	def details(self):
		print("My name is {}".format(self.name))
		print("IdNumber: {}".format(self.idnumber))
		print("Post: {}".format(self.post))


"""creation of an object variable or an instance"""
a = Employee('Rahul', 886012, 200000, "Intern")

"""calling a function of the class Person using its instance"""
a.display()
a.details()

```
In the above example, we have created two classes i.e. Person (parent class) and Employee (Child Class). The Employee class inherits from the Person class. We can use the methods of the person class through the employee class as seen in the display function in the above code. A child class can also modify the behavior of the parent class as seen through the details() method.

## the `super()`:
In Python, the super() function is used to refer to the parent class or superclass. It allows you to call methods defined in the superclass from the subclass, enabling you to extend and customize the functionality inherited from the parent class.

In the given example, The Emp class has an __init__ method that initializes the id, and name and Adds attributes. The Freelance class inherits from the Emp class and adds an additional attribute called Emails. It calls the parent class’s __init__ method super() to initialize the inherited attribute.

```python
class Emp():
    def __init__(self, id, name, Add):
        self.id = id
        self.name = name
        self.Add = Add
 
"""Class freelancer inherits EMP"""
class Freelance(Emp):
    def __init__(self, id, name, Add, Emails):
        super().__init__(id, name, Add)
        self.Emails = Emails
 
Emp_1 = Freelance(103, "Suraj kr gupta", "Noida" , "KKK@gmails")
print('The ID is:', Emp_1.id)
print('The Name is:', Emp_1.name)
print('The Address is:', Emp_1.Add)
print('The Emails is:', Emp_1.Emails)
```
### What is the super () method used for?
A method from a parent class can be called in Python using the super() function. It’s typical practice in object-oriented programming to call the methods of the superclass and enable method overriding and inheritance. Even if the current class has replaced those methods with its own implementation, calling super() allows you to access and use the parent class’s methods. By doing this, you may enhance and modify the parent class’s behavior while still gaining from it.

#### Benefits of Super Function
- Need not remember or specify the parent class name to access its methods. This function can be used both in single and multiple inheritances.
- This implements modularity (isolating changes) and code reusability as there is no need to rewrite the entire function.
- The super function in Python is called dynamically because Python is a dynamic language, unlike other languages.

Python has a reserved method called `__init__`. In Object-Oriented Programming, it is referred to as a constructor. When this method is called it allows the class to initialize the attributes of the class. In an inherited subclass, a parent class can be referred to with the use of the super() function. __The super function returns a temporary object of the superclass that allows access to all of its methods to its child class__.

## Single level Inheritance

Let’s take the example of animals. Dogs, cats, and cows are part of animals. They also share common characteristics like –  

- They are mammals.
- They have a tail and four legs.
- They are domestic animals.

So, the classes dogs, cats, and horses are a subclass of animal class. This is an example of single inheritance because many subclasses is inherited from a single-parent class.

``` python
class Animals:
    # Initializing constructor
    def __init__(self):
        self.legs = 4
        self.domestic = True
        self.tail = True
        self.mammals = True
 
    def isMammal(self):
        if self.mammals:
            print("It is a mammal.")
 
    def isDomestic(self):
        if self.domestic:
            print("It is a domestic animal.")
 
class Dogs(Animals):
    def __init__(self):
        super().__init__()
 
    def isMammal(self):
        super().isMammal()
 
class Horses(Animals):
    def __init__(self):
        super().__init__()
 
    def hasTailandLegs(self):
        if self.tail and self.legs == 4:
            print("Has legs and tail")
 
""" Driver code """
Tom = Dogs()
Tom.isMammal()
Bruno = Horses()
Bruno.hasTailandLegs()
```

## Multiple Inheritance

Let’s take another example of a super function, Suppose a class can fly and can swim inherit from a mammal class and these classes are inherited by the animal class. So the animal class inherits from the multiple base classes. Let’s see the use of Python super with arguments in this case.

```python
class Mammal():
 
    def __init__(self, name):
        print(name, "Is a mammal")
 
class canFly(Mammal):
 
    def __init__(self, canFly_name):
        print(canFly_name, "cannot fly")
 
        # Calling Parent class
        # Constructor
        super().__init__(canFly_name)
 
class canSwim(Mammal):
 
    def __init__(self, canSwim_name):
 
        print(canSwim_name, "cannot swim")
 
        super().__init__(canSwim_name)
 
class Animal(canFly, canSwim):
 
    def __init__(self, name):
        super().__init__(name)
 

Carol = Animal("Dog")
```

output: The class Animal inherits from two-parent classes – canFly and canSwim. So, the subclass instance Carol can access both of the parent class constructors. 
```
Dog cannot fly
Dog cannot swim
Dog Is a mammal
```

## Multiple inheritance

Let’s take another example of a super function, suppose a class can swim is inherited by canFly, canFly from the mammal class. So the mammal class inherits from the Multi-Level inheritance. Let’s see the use of Python super with arguments in this case.
```python
class Mammal():
 
    def __init__(self, name):
        print(name, "Is a mammal")
 
 
class canFly(Mammal):
 
    def __init__(self, canFly_name):
        print(canFly_name, "cannot fly")
 
        # Calling Parent class
        # Constructor
        super().__init__(canFly_name)
 
 
class canSwim(canFly):
 
    def __init__(self, canSwim_name):
 
        print(canSwim_name, "cannot swim")
 
        super().__init__(canSwim_name)
 
 
class Animal(canSwim):
 
    def __init__(self, name):
 
        # Calling the constructor
        # of both the parent
        # class in the order of
        # their inheritance
        super().__init__(name)
 
 

Carol = Animal("Dog")
```

## Further reading 

[Method resolution order in python inheritance - MRO](https://www.geeksforgeeks.org/method-resolution-order-in-python-inheritance/)