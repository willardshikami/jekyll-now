---
layout: post
title: Objects and Classes
---

Java is an Object-Oriented Language. As a language that has the Object Oriented feature, Java supports the following fundamental concepts:<br />

1. Polymorphism <br />
2. Inheritance <br />
3. Encapsulation <br />
4. Abstraction <br />
5. Classes <br />
6. Objects <br />
7. Instance <br />
8. Method <br />
9. Message Parsing <br />
In this chapter, we will look into the concepts Classes and Objects.<br />
**Object** - Objects have states and behaviors. Example: A dog has states - color, name, breed as well as behaviors -wagging, barking, eating. An object is an instance of a class. <br />
**Class** - A class can be defined as a template/blue print that describes the behaviors/states that object of its type support.<br />
**Objects in Java:**<br />
Let us now look deep into what are objects. If we consider the real-world we can find many objects around us, Cars, Dogs, Humans, etc. All these objects have a state and behavior.<br />
If we consider a dog, then its state is - name, breed, color, and the behavior is - barking, wagging, running<br />
If you compare the software object with a real world object, they have very similar characteristics.<br />
Software objects also have a state and behavior. A software object's state is stored in fields and behavior is shown via methods.<br />
So in software development, methods operate on the internal state of an object and the object-to-object communication is done via methods.<br />
**Classes in Java:**<br />
A class is a blue print from which individual objects are created.<br />
A sample of a class is given below: <br />
A class can contain any of the following variable types.<br />
**Local variables:** Variables defined inside methods, constructors or blocks are called local variables. The variable will be declared and initialized within the method and the variable will be destroyed when the method has completed.<br />
**Instance variables:** Instance variables are variables within a class but outside any method. These variables are initialized when the class is instantiated. Instance variables can be accessed from inside any method, constructor or blocks of that particular class.<br />
**Class variables:** Class variables are variables declared with in a class, outside any method, with the static keyword.<br />
A class can have any number of methods to access the value of various kinds of methods. In the above example, barking(), hungry() and sleeping() are methods.<br />
Below mentioned are some of the important topics that need to be discussed when looking into classes of the Java Language.<br />
**Constructors:**<br />
When discussing about classes, one of the most important sub topic would be constructors. Every class has a constructor. If we do not explicitly write a constructor for a class the Java compiler builds a default constructor for that class.<br />
Each time a new object is created, at least one constructor will be invoked. The main rule of constructors is that they should have the same name as the class. A class can have more than one constructor.<br />
Java also supports Singleton Classes where you would be able to create only one instance of a class.<br />
Note: We have two different types of constructors we are going to discuss constructors in detail in coming chapters.<br />
**Creating an Object:**<br />
As mentioned previously, a class provides the blueprints for objects. So basically an object is created from a class. In Java, the new key word is used to create new objects. <br />
There are three steps when creating an object from a class:<br />
**Declaration:** A variable declaration with a variable name with an object type.<br />
**Instantiation:** The 'new' key word is used to create the object.<br />
**Initialization:** The 'new' keyword is followed by a call to a constructor. This call initializes the new object.<br />
**Accessing Instance Variables and Methods:**
Instance variables and methods are accessed via created objects. To access an instance variable the fully qualified path should be as follows:<br />
**Source file declaration rules:**<br />
As the last part of this section let's now look into the source file declaration rules. These rules are essential when declaring classes, import statements and package statements in a source file.<br />
There can be only one public class per source file.<br />
A source file can have multiple non public classes.<br />
The public class name should be the name of the source file as well which should be appended by .java at the end. For example: the class name is public class Employee{} then the source file should be as Employee.java.<br />
If the class is defined inside a package, then the package statement should be the first statement in the source file.<br />
If import statements are present then they must be written between the package statement and the class declaration. If there are no package statements then the import statement should be the first line in the source file. <br />
Import and package statements will imply to all the classes present in the source file. It is not possible to declare different import and/or package statements to different classes in the source file.<br />
Classes have several access levels and there are different types of classes; abstract classes, final classes, etc. we will be explaining about all these in the access modifiers chapter.<br />
Apart from the above mentioned types of classes, Java also has some special classes called Inner classes and Anonymous classes.<br />
**Java Package:**<br />
In simple, it is a way of categorizing the classes and interfaces. When developing applications in Java, hundreds of classes and interfaces will be written, therefore categorizing these classes is a must as well as makes life much easier.
**Import statements:**<br />
In Java if a fully qualified name, which includes the package and the class name, is given then the compiler can easily locate the source code or classes. Import statement is a way of giving the proper location for the compiler to find that particular class.<br />
