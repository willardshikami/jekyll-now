---
layout: post
title: Getter and Setter
---

Encapsulation is among four of the fundamental of OOP in java. It involves hiding variables of a specific class from other classes.<br /> These variables can only be accessed through methods in their current class. <br />



The following example shows how achieve encapsulation

    public class EncapTest {

    private String name ;

    private String idNum ;

    private int age ;

    public int getAge (){

    return age ;
        }
        
    public String getName (){
        return name ;
    }
    
    public String getIdNum (){
        return idNum ;
    }
    public void setAge ( int newAge ){
        age = newAge ;
    }
    public void setName ( String newName
    name = newName ;
        }
    public void setIdNum ( String newId
        idNum = newId ;
        }
    }

Any class that needs to access these variables we will need to use methods called getters and setters. <br/>
Getters and Setters enable you to read and write these
From the above example of encapsulation, these values can be attained using the following method.<br/>

    public class RunEncap {
    public static void main ( String arg
    EncapTest encap = new EncapTest
    encap . setName( "James" );
    encap . setAge ( 20 );
    encap . setIdNum ( "12343ms" );
    System . out . print( "Name : " + en


The me the method above will display the following result<br />
Name: James Age: 20<br />

Getter and Setter make APIs more stable. For instance, consider a field public in a class which is accessed by other classes.<br /> Now later on, you want to add any extra logic while getting and setting the variable. This will impact the existing client that uses the API. So any changes to this public field will require change to each class that refers it.<br /> On the contrary, with getter and setter methods, one can easily add some logic like cache some data, lazily initialize it later. Moreover, one can fire a property changed event if the new value is different from the previous value.<br /> All this will be seamless to the class that gets value using getter setter method 
