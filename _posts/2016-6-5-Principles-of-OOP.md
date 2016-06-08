---
layout: post
title: Principles of Object Oriented Programming
---

ENCAPSULATION
This is one of the four fundamental OOP concepts. The other three are inheritance, polymorphism, and abstraction.
Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as as single unit. In encapsulation the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class, therefore it is also known as data hiding.
To achieve encapsulation in Java
Declare the variables of a class as private.
Provide public setter and getter methods to modify and view the variables values.
Example:
Below given is an example that demonstrates how to achieve Encapsulation in Java:
/* File name : EncapTest.java */
public class EncapTest{

   private String name;
   private String idNum;
   private int age;

   public int getAge(){
      return age;
   }

   public String getName(){
      return name;
   }

   public String getIdNum(){
      return idNum;
   }

   public void setAge( int newAge){
      age = newAge;
   }

   public void setName(String newName){
      name = newName;
   }

   public void setIdNum( String newId){
      idNum = newId;
   }
}
The public setXXX() and getXXX() methods are the access points of the instance variables of the EncapTest class. Normally, these methods are referred as getters and setters. Therefore any class that wants to access the variables should access them through these getters and setters.
The variables of the EncapTest class can be accessed as below::
/* File name : RunEncap.java */
public class RunEncap{

   public static void main(String args[]){
      EncapTest encap = new EncapTest();
      encap.setName("James");
      encap.setAge(20);
      encap.setIdNum("12343ms"); 

      System.out.print("Name : " + encap.getName() + " Age : " + encap.getAge());
    }
}
This would produce the following result:
Name : James Age : 20
Benefits of Encapsulation:
The fields of a class can be made read-only or write-only.
A class can have total control over what is stored in its fields.
The users of a class do not know how the class stores its data. A class can change the data type of a field and users of the class do not need to change any of their code.

ABSTRACTION
Abstraction is the quality of dealing with ideas rather than events. for example when you consider the case of e-mail, complex details such as what happens soon you send an e-mail, the protocol your email server uses are hidden from the user, therefore to send an e-mail you just need to type the content, mention the address of the receiver and click send.
like wise in Object oriented programming Abstraction is a process of hiding the implementation details from the user, only the functionality will be provided to the user. In other words user will have the information on what the object does instead of how it does it.
In Java Abstraction is achieved using Abstract classes, and Interfaces.
Abstract Class 
A class which contains the abstract keyword in its declaration is known as abstract class.
Abstract classes may or may not contain abstract methods ie., methods with out body ( public void get(); )
But, if a class have at least one abstract method, then the class must be declared abstract.
If a class is declared abstract it cannot be instantiated.
To use an abstract class you have to inherit it from another class, provide implementations to the abstract methods in it.
If you inherit an abstract class you have to provide implementations to all the abstract methods in it.
Example
This section provides you an example of the abstract class to create an abstract class just use the abstract keyword before the class keyword, in the class declaration .
/* File name : Employee.java */
public abstract class Employee
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
   public double computePay()
   {
     System.out.println("Inside Employee computePay");
     return 0.0;
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
You can observe that except abstract methods the Employee class is same as normal class in Java. The class is now abstract, but it still has three fields, seven methods, and one constructor.
Now you can try to instantiate the Employee class as shown below:
/* File name : AbstractDemo.java */
public class AbstractDemo
{
   public static void main(String [] args)
   {
      /* Following is not allowed and would raise error */
      Employee e = new Employee("George W.", "Houston, TX", 43);

      System.out.println("\n Call mailCheck using Employee reference--");
      e.mailCheck();
    }
}
When you compile the above class, it gives you the following error:
Employee.java:46: Employee is abstract; cannot be instantiated
      Employee e = new Employee("George W.", "Houston, TX", 43);
                   ^
1 error
Inheriting the Abstract Class:
We can inherit the properties of Employee class just like concrete class as shown below:
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
Here, you cannot instantiate the Employee class, but you can instantiate the Salary Class, and using this instance you can access the all the three fields and seven methods of Employee class as shown below.
/* File name : AbstractDemo.java */
public class AbstractDemo
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
This produces the following result:
Constructing an Employee
Constructing an Employee
Call mailCheck using  Salary reference --
Within mailCheck of Salary class
ailing check to Mohd Mohtashim with salary 3600.0

Call mailCheck using Employee reference--
Within mailCheck of Salary class
ailing check to John Adams with salary 2400.
Abstract Methods:
If you want a class to contain a particular method but you want the actual implementation of that method to be determined by child classes, you can declare the method in the parent class as abstract.
abstract keyword is used to declare the method as abstract.
You have to place the abstract keyword before the method name in the method declaration.
An abstract method contains a method signature, but no method body.
Instead of curly braces an abstract method will have a semoi colon ( ; ) at the end.
Below given is an example of the abstract method.
public abstract class Employee
{
   private String name;
   private String address;
   private int number;
   
   public abstract double computePay();
   
   //Remainder of class definition
}
Declaring a method as abstract has two consequences:
The class containing it must be declared as abstract. 
Any class inheriting the current class must either override the abstract method or declare itself as abstract.
Note: Eventually, a descendant class has to implement the abstract method; otherwise, you would have a hierarchy of abstract classes that cannot be instantiated.
Suppose Salary class is inherits the Employee class, then it should implement the computePay() method as shown below:
/* File name : Salary.java */
public class Salary extends Employee
{
   private double salary; // Annual salary
  
   public double computePay()
   {
      System.out.println("Computing salary pay for " + getName());
      return salary/52;
   }

   //Remainder of class definition

INHERITANCE
Inheritance can be defined as the process where one class acquires the properties (methods and fields) of another. With the use of inheritance the information is made manageable in a hierarchical order.
The class which inherits the properties of other is known as subclass (derived class, child class) and the class whose properties are inherited is known as superclass (base class, parent class).
extends Keyword
extends is the keyword used to inherit the properties of a class. Below given is the syntax of extends keyword.
class Super{
   .....
   .....
}

class Sub extends Super{
   .....
   .....

}
Sample Code
Below given is an example demonstrating Java inheritance. In this example you can observe two classes namely Calculation and My_Calculation.
Using extends keyword the My_Calculation inherits the methods addition() and Subtraction() of Calculation class.
Copy and paste the program given below in a file with name My_Calculation.java
class Calculation{ 
   int z;
        
   public void addition(int x, int y){
      z = x+y;
      System.out.println("The sum of the given numbers:"+z);
   }
        
   public void Subtraction(int x,int y){
      z = x-y;
      System.out.println("The difference between the given numbers:"+z);
   }
   
}

public class My_Calculation extends Calculation{    
  
   public void multiplication(int x, int y){
      z = x*y;
      System.out.println("The product of the given numbers:"+z);
   }
        
   public static void main(String args[]){
      int a = 20, b = 10;
      My_Calculation demo = new My_Calculation();
      demo.addition(a, b);
      demo.Subtraction(a, b);
      demo.multiplication(a, b);      
   }

}
Compile and execute the above code as shown below
javac My_Calculation.java
java My_Calculation
After executing the program it will produce the following result.
The sum of the given numbers:30
The difference between the given numbers:10
The product of the given numbers:200
In the given program when an object to My_Calculation class is created, a copy of the contents of the super class is made with in it. That is why, using the object of the subclass you can access the members of a super class.
 
The Superclass reference variable can hold the subclass object, but using that variable you can access only the members of the superclass, so to access the members of both classes it is recommended to always create reference variable to the subclass.
If you consider the above program you can instantiate the class as given below as well. But using the superclass reference variable ( cal in this case ) you cannot call the method multiplication(), which belongs to the subclass My_Calculation.
Calculation cal = new My_Calculation();
demo.addition(a, b);
demo.Subtraction(a, b);
Note − A subclass inherits all the members (fields, methods, and nested classes) from its superclass. Constructors are not members, so they are not inherited by subclasses, but the constructor of the superclass can be invoked from the subclass.
The super keyword
The super keyword is similar to this keyword following are the scenarios where the super keyword is used.
It is used to differentiate the members of superclass from the members of subclass, if they have same names.
It is used to invoke the superclass constructor from subclass.
Differentiating the members
If a class is inheriting the properties of another class. And if the members of the superclass have the names same as the sub class, to differentiate these variables we use super keyword as shown below.
super.variable
super.method();
Sample Code
This section provides you a program that demonstrates the usage of the super keyword.
In the given program you have two classes namely Sub_class and Super_class, both have a method named display() with different implementations, and a variable named num with different values. We are invoking display() method of both classes and printing the value of the variable num of both classes, here you can observe that we have used super key word to differentiate the members of super class from sub class.
Copy and paste the program in a file with name Sub_class.java.
class Super_class{

   int num = 20;
   
   //display method of superclass
   public void display(){   
      System.out.println("This is the display method of superclass");
   }    

}

public class Sub_class extends Super_class {

   int num = 10;
   
   //display method of sub class
   public void display(){
      System.out.println("This is the display method of subclass");
   }
   
   public void my_method(){
          
      //Instantiating subclass
      Sub_class sub = new Sub_class();
          
      //Invoking the display() method of sub class
      sub.display();
          
      //Invoking the display() method of superclass
      super.display();
          
      //printing the value of variable num of subclass
      System.out.println("value of the variable named num in sub class:"+ sub.num);
                  
      //printing the value of variable num of superclass
      System.out.println("value of the variable named num in super class:"+ super.num);     
   }
   
   public static void main(String args[]){
      Sub_class obj = new Sub_class();
      obj.my_method();
      
   }
}
Compile and execute the above code using the following syntax.
javac Super_Demo
java Super
On executing the program you will get the following result −
This is the display method of subclass
This is the display method of superclass
value of the variable named num in sub class:10
value of the variable named num in super class:20
Invoking Superclass constructor
If a class is inheriting the properties of another class, the subclass automatically acquires the default constructor of the super class. But if you want to call a parametrized constructor of the super class, you need to use the super keyword as shown below.
super(values);
Sample Code
The program given in this section demonstrates how to use the super keyword to invoke the parametrized constructor of the superclass. This program contains a super class and a sub class, where the super class contains a parametrized constructor which accepts a string value, and we used the super keyword to invoke the parametrized constructor of the super class.
Copy and paste the below given program in a file with name Subclass.java
class Superclass{
   
   int age;

   Superclass(int age){
      this.age = age;            
   }

   public void getAge(){
      System.out.println("The value of the variable named age in super class is: " +age);
   }

}

public class Subclass extends Superclass {
   
   Subclass(int age){
      super(age);
   }

   public static void main(String argd[]){
      Subclass s = new Subclass(24);
      s.getAge();
   }

}
Compile and execute the above code using the following syntax.
javac Subclass
java Subclass
On executing the program you will get the following result −
The value of the variable named age in super class is: 24
IS-A Relationship
IS-A is a way of saying : This object is a type of that object. Let us see how the extends keyword is used to achieve inheritance.
public class Animal{
}

public class Mammal extends Animal{
}

public class Reptile extends Animal{
}

public class Dog extends Mammal{
}
Now, based on the above example, In Object Oriented terms, the following are true −
Animal is the superclass of Mammal class.
Animal is the superclass of Reptile class.
Mammal and Reptile are subclasses of Animal class.
Dog is the subclass of both Mammal and Animal classes.
Now, if we consider the IS-A relationship, we can say −
Mammal IS-A Animal
Reptile IS-A Animal
Dog IS-A Mammal
Hence : Dog IS-A Animal as well
With use of the extends keyword the subclasses will be able to inherit all the properties of the superclass except for the private properties of the superclass.
We can assure that Mammal is actually an Animal with the use of the instance operator.
Example
class Animal{
}

class Mammal extends Animal{
}

class Reptile extends Animal{
}

public class Dog extends Mammal{

   public static void main(String args[]){

      Animal a = new Animal();
      Mammal m = new Mammal();
      Dog d = new Dog();

      System.out.println(m instanceof Animal);
      System.out.println(d instanceof Mammal);
      System.out.println(d instanceof Animal);
   }
}
This would produce the following result −
true
true
true
Since we have a good understanding of the extends keyword let us look into how the implements keyword is used to get the IS-A relationship.
Generally, the implements keyword is used with classes to inherit the properties of an interface. Interfaces can never be extended by a class.
Example
public interface Animal {
}

public class Mammal implements Animal{
}

public class Dog extends Mammal{
}
The instanceof Keyword
Let us use the instanceof operator to check determine whether Mammal is actually an Animal, and dog is actually an Animal
interface Animal{}

class Mammal implements Animal{}

public class Dog extends Mammal{

   public static void main(String args[]){

      Mammal m = new Mammal();
      Dog d = new Dog();

      System.out.println(m instanceof Animal);
      System.out.println(d instanceof Mammal);
      System.out.println(d instanceof Animal);
   }
} 
This would produce the following result:
true
true
true
HAS-A relationship
These relationships are mainly based on the usage. This determines whether a certain class HAS-A certain thing. This relationship helps to reduce duplication of code as well as bugs.
Lets us look into an example −
public class Vehicle{}
public class Speed{}

public class Van extends Vehicle{
        private Speed sp;
} 
This shows that class Van HAS-A Speed. By having a separate class for Speed, we do not have to put the entire code that belongs to speed inside the Van class., which makes it possible to reuse the Speed class in multiple applications.
In Object-Oriented feature, the users do not need to bother about which object is doing the real work. To achieve this, the Van class hides the implementation details from the users of the Van class. So basically what happens is the users would ask the Van class to do a certain action and the Van class will either do the work by itself or ask another class to perform the action.
Types of inheritance
There are various types of inheritance as demonstrated below.
 
A very important fact to remember is that Java does not support multiple inheritance. This means that a class cannot extend more than one class. Therefore following is illegal −
public class extends Animal, Mammal{} 
However, a class can implement one or more interfaces. This has made Java get rid of the impossibility of multiple inheritance.

POLYMORPHISM
Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object.
Any Java object that can pass more than one IS-A test is considered to be polymorphic. In Java, all Java objects are polymorphic since any object will pass the IS-A test for their own type and for the class Object.
It is important to know that the only possible way to access an object is through a reference variable. A reference variable can be of only one type. Once declared, the type of a reference variable cannot be changed.
The reference variable can be reassigned to other objects provided that it is not declared final. The type of the reference variable would determine the methods that it can invoke on the object.
A reference variable can refer to any object of its declared type or any subtype of its declared type. A reference variable can be declared as a class or interface type.
Example:
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
Virtual Methods:
In this section, I will show you how the behaviour of overridden methods in Java allows you to take advantage of polymorphism when designing your classes.
We already have discussed method overriding, where a child class can override a method in its parent. An overridden method is essentially hidden in the parent class, and is not invoked unless the child class uses the super keyword within the overriding method.
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
