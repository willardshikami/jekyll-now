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
3. The users of a class do not know how the class stores its data. A class can change the data type of a field and users of the class do not need to change any of their code.<br />

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
class Super{
   .....
   .....
}<br />

class Sub extends Super{
   .....
   .....

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
 
A very important fact to remember is that Java does not support multiple inheritance. This means that a class cannot extend more than one class. Therefore following is illegal −
public class extends Animal, Mammal{} 
However, a class can implement one or more interfaces. This has made Java get rid of the impossibility of multiple inheritance.

**POLYMORPHISM**<br />
Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object.<br />
Any Java object that can pass more than one IS-A test is considered to be polymorphic. In Java, all Java objects are polymorphic since any object will pass the IS-A test for their own type and for the class Object.<br />
It is important to know that the only possible way to access an object is through a reference variable. A reference variable can be of only one type. Once declared, the type of a reference variable cannot be changed.<br />
The reference variable can be reassigned to other objects provided that it is not declared final. The type of the reference variable would determine the methods that it can invoke on the object.<br />
A reference variable can refer to any object of its declared type or any subtype of its declared type. A reference variable can be declared as a class or interface type.<br />
Example:<br />
Let us look at an example.
public interface Vegetarian{}
public class Animal{}
public class Deer extends Animal implements Vegetarian{}
Now, the Deer class is considered to be polymorphic since this has multiple inheritance. Following are true for the above example:
A Deer IS-A Animal
A Deer IS-A Vegetarian
A Deer IS-A Deer 
A Deer IS-A Object
When we apply the reference variable facts to a Deer object reference, the following declarations are legal:
Deer d = new Deer();
Animal a = d;
Vegetarian v = d;
Object o = d;
All the reference variables d,a,v,o refer to the same Deer object in the heap.
**Virtual Methods:**<br />
In this section, I will show you how the behaviour of overridden methods in Java allows you to take advantage of polymorphism when designing your classes.<br />
We already have discussed method overriding, where a child class can override a method in its parent. An overridden method is essentially hidden in the parent class, and is not invoked unless the child class uses the super keyword within the overriding method.<br />
/* File name : Employee.java */
public class Employee
{
   private String name;
   private String address;
   private int number;
   public Employee(String name, String address, int number)
   {
      System.out.println("Constructing an Employee");
      this.name = name;
      this.address = address;
      this.number = number;
   }
   public void mailCheck()
   {
      System.out.println("Mailing a check to " + this.name
       + " " + this.address);
   }
   public String toString()
   {
      return name + " " + address + " " + number;
   }
   public String getName()
   {
      return name;
   }
   public String getAddress()
   {
      return address;
   }
   public void setAddress(String newAddress)
   {
      address = newAddress;
   }
   public int getNumber()
   {
     return number;
   }
}
Now suppose we extend Employee class as follows:
/* File name : Salary.java */
public class Salary extends Employee
{
   private double salary; //Annual salary
   public Salary(String name, String address, int number, double
      salary)
   {
       super(name, address, number);
       setSalary(salary);
   }
   public void mailCheck()
   {
       System.out.println("Within mailCheck of Salary class ");
       System.out.println("Mailing check to " + getName()
       + " with salary " + salary);
   }
   public double getSalary()
   {
       return salary;
   }
   public void setSalary(double newSalary)
   {
       if(newSalary >= 0.0)
       {
          salary = newSalary;
       }
   }
   public double computePay()
   {
      System.out.println("Computing salary pay for " + getName());
      return salary/52;
   }
}
Now, you study the following program carefully and try to determine its output:
/* File name : VirtualDemo.java */
public class VirtualDemo
{
   public static void main(String [] args)
   {
      Salary s = new Salary("Mohd Mohtashim", "Ambehta, UP", 3, 3600.00);
      Employee e = new Salary("John Adams", "Boston, MA", 2, 2400.00);
      System.out.println("Call mailCheck using Salary reference --");
      s.mailCheck();
      System.out.println("\n Call mailCheck using Employee reference--");
      e.mailCheck();
    }
}
This would produce the following result:
Constructing an Employee
Constructing an Employee
Call mailCheck using Salary reference --
Within mailCheck of Salary class
ailing check to Mohd Mohtashim with salary 3600.0

Call mailCheck using Employee reference--
Within mailCheck of Salary class
ailing check to John Adams with salary 2400.0
Here, we instantiate two Salary objects . one using a Salary reference s, and the other using an Employee reference e.
While invoking s.mailCheck() the compiler sees mailCheck() in the Salary class at compile time, and the JVM invokes mailCheck() in the Salary class at run time.
Invoking mailCheck() on e is quite different because e is an Employee reference. When the compiler sees e.mailCheck(), the compiler sees the mailCheck() method in the Employee class.
Here, at compile time, the compiler used mailCheck() in Employee to validate this statement. At run time, however, the JVM invokes mailCheck() in the Salary class.
This behavior is referred to as virtual method invocation, and the methods are referred to as virtual methods. All methods in Java behave in this manner, whereby an overridden method is invoked at run time, no matter what data type the reference is that was used in the source code at compile time.
