---
layout: post
title: Principles of Object Oriented Programming
---

**ENCAPSULATION**<br />
This is one of the four fundamental OOP concepts. The other three are inheritance, polymorphism, and abstraction.<br />
Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as as single unit. In encapsulation the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class, therefore it is also known as data hiding.<br />
To achieve encapsulation in Java<br />
Declare the variables of a class as private.<br />
Provide public setter and getter methods to modify and view the variables values.<br />

**Benefits of Encapsulation:**<br />
1. The fields of a class can be made read-only or write-only.<br />
2. A class can have total control over what is stored in its fields.<br />
3. The users of a class do not know how the class stores its data. A class can change the data type of a field and users of the    class do not need to change any of their code.<br />

**ABSTRACTION**<br />
Abstraction is the quality of dealing with ideas rather than events. for example when you consider the case of e-mail, complex details such as what happens soon you send an e-mail, the protocol your email server uses are hidden from the user, therefore to send an e-mail you just need to type the content, mention the address of the receiver and click send.<br />
like wise in Object oriented programming Abstraction is a process of hiding the implementation details from the user, only the functionality will be provided to the user. In other words user will have the information on what the object does instead of how it does it.<br />
In Java Abstraction is achieved using Abstract classes, and Interfaces.<br />

**Abstract Class** <br />
A class which contains the abstract keyword in its declaration is known as abstract class.<br />
Abstract classes may or may not contain abstract methods ie., methods with out body ( public void get(); )<br />
But, if a class have at least one abstract method, then the class must be declared abstract.<br />
If a class is declared abstract it cannot be instantiated.<br />
To use an abstract class you have to inherit it from another class, provide implementations to the abstract methods in it.
If you inherit an abstract class you have to provide implementations to all the abstract methods in it.<br />

**Abstract Methods:**<br />
If you want a class to contain a particular method but you want the actual implementation of that method to be determined by child classes, you can declare the method in the parent class as abstract.<br />
abstract keyword is used to declare the method as abstract.<br />
You have to place the abstract keyword before the method name in the method declaration.<br />
An abstract method contains a method signature, but no method body.<br />
Instead of curly braces an abstract method will have a semoi colon ( ; ) at the end.

**INHERITANCE**
Inheritance can be defined as the process where one class acquires the properties (methods and fields) of another. With the use of inheritance the information is made manageable in a hierarchical order.<br />
The class which inherits the properties of other is known as subclass (derived class, child class) and the class whose properties are inherited is known as superclass (base class, parent class).<br />

**extends Keyword**<br />
extends is the keyword used to inherit the properties of a class. Below given is the syntax of extends keyword.<br />
class Super{<br />
   .....<br />
   .....<br />
}<br />

class Sub extends Super{<br />
   .....<br />
   .....<br />

}<br />

**Note** − A subclass inherits all the members (fields, methods, and nested classes) from its superclass. Constructors are not members, so they are not inherited by subclasses, but the constructor of the superclass can be invoked from the subclass.<br />

**The super keyword**<br />
The super keyword is similar to this keyword following are the scenarios where the super keyword is used.<br />
It is used to differentiate the members of superclass from the members of subclass, if they have same names.<br />
It is used to invoke the superclass constructor from subclass.<br />

**Differentiating the members**<br />
If a class is inheriting the properties of another class. And if the members of the superclass have the names same as the sub class, to differentiate these variables we use super keyword as shown below.
super.variable<br />
super.method();<br />

**Invoking Superclass constructor**<br />
If a class is inheriting the properties of another class, the subclass automatically acquires the default constructor of the super class. But if you want to call a parametrized constructor of the super class, you need to use the super keyword as shown below.<br />
super(values);<br />

**Types of inheritance**<br />
There are various types of inheritance as demonstrated below.<br />
 
A very important fact to remember is that Java does not support multiple inheritance. This means that a class cannot extend more than one class.<br />
However, a class can implement one or more interfaces. This has made Java get rid of the impossibility of multiple inheritance.<br />

**POLYMORPHISM**<br />
Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object.<br />
Any Java object that can pass more than one IS-A test is considered to be polymorphic. In Java, all Java objects are polymorphic since any object will pass the IS-A test for their own type and for the class Object.<br />
It is important to know that the only possible way to access an object is through a reference variable. A reference variable can be of only one type. Once declared, the type of a reference variable cannot be changed.<br />
The reference variable can be reassigned to other objects provided that it is not declared final. The type of the reference variable would determine the methods that it can invoke on the object.<br />
A reference variable can refer to any object of its declared type or any subtype of its declared type. A reference variable can be declared as a class or interface type.<br />

This behavior is referred to as virtual method invocation, and the methods are referred to as virtual methods. All methods in Java behave in this manner, whereby an overridden method is invoked at run time, no matter what data type the reference is that was used in the source code at compile time.<br /> 
