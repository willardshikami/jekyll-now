---
layout: post
title: Object Oriented Programming 
---
Object Oriented programming can be summed up as putting data before action.<br />
On the other hand, in Procedural Programming, the problem is approached by disintegrating it into a series of actions also known as functions.<br />
In Object Oriented Programming it is approached by first trying to disintegrate it into data types. <br />
In Procedural Programming we think in terms of functions and later consider the actual data that the function act upon.<br />
In Object Oriented Programming we come up with data types and the decide on the operations that need to be associated with those data types. <br />
Many programming languages are considered as Object Oriented Programs as they consist of features that encourage the programmer to program in an object.<br />

**Class** – Definition of a data type. Each data type is defined by the number that make it up. <br />
Numbers come in two basic kinds, Fields and Methods<br />
**Fields** – Data members that actually make up the type.<br />
**Method** – Functions associated with the class. They are the operations for acting on the data.<br />

**Objects/Instances** – These are actual piece of data in a class. <br />

When we produce an instance from a class, that instance gets its own field that are different from the fields of all other instances and class.<br />

**Encapsulation**<br /> 
The fields of an object/instance should only be read and written by methods of that object class.<br />
Following the encapsulation principle makes sure that our code is neatly and clearly modularized allowing us to easily make changes to add features and fix bugs.<br />
Failing to follow the principle, data in our code can easily be read and written from all different places. <br />Therefore the code will be extremely difficult to understand, fix and modify.<br /> 
In encapsulation you can only make distinction between public and private members of the class.<br />
**Public members** of the class are visible anywhere therefore it is okay to access them from outside their own class.<br />
**Private members** are only to be accessed by methods of the same class.<br />
When strictly following the principals of encapsulation, all fields should be kept private.<br />
Methods can either be private or public.<br />

**Inheritance**<br />
in inheritance, some data types and classes may overlap. One data type can have all the dame things found in another.<br />
When working with an existing code/program, adding a new feature can be implemented successfully by taking an existing class in code and extending, i.e. producing a subtype if that class.<br />
When it works well, it helps focus on describing the code for the new functionality not having to duplicate already existing stuff. <br />
Inheritance should not be used all over the place. 
The rule to keep while thinking of using an instance is the relationship between the two classes, i.e. the  instances of the child class could be considered more as specific versions of the parent class.<br />

**Multiple inheritance.**<br />
In some languages in inheritance, one class may inherit from more than one other class.<br />
Most of the languages do not allow multiple inheritance.
No languages however allow circular inheritance, that is directly inheriting from itself. <br />
In other programming languages, every class is required to inherit from at least one other class and by default that class is a special class called object class which is built into the language.<br />

**Overriding** <br />
This means to redefine an inherited method. <br />

**Class member**<br />
In most languages, class member maybe accessed via instances of the class as if they were instance members.<br />

**Static fields/Class field** is a global variable that lives inside the name space of a class.<br />
**Static methods/Class method** is a procedural function that also lives inside the name space of a class.<br /> 

Using a lot of class fields and class methods in your code makes it not fully Object Oriented, it is just procedural programming in disguise.<br />

**Constructor**<br />
A method that is run when we instantiate a class.<br />
In most cases the constructor gives the fields initial default values while in other cases the constructor might do more complex things like running real code.<br />

**Interface**<br />
Two different classes that share a set of methods in common, these set of methods are known as Interface.<br />
We can interact with any objects or classes that share an interface the same way with the shared set of methods.<br /> 

**Abstract class**<br />
This is class that is not meant to be instantiated instead it serves as an ancestor for the other classes.<br />

**Prototypical inheritance**<br />
in prototypical inheritance, there is no formal notion of classes, just objects linked together and it is up to the programmer to treat certain objects like classes, give them methods and fields and then produce instances that link back to that object.  <br />
