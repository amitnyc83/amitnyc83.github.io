---
layout: post
title:      "Javascript Model Objects vs Ruby Classes"
date:       2019-03-25 14:59:26 +0000
permalink:  javascript_model_objects_vs_ruby_classes
---


When i was about to start learning about Javascript Model Objects, i was telling myself how much more can my mind absorb after ruby. Let me tell you, there are lots of similarities between Javascript and Ruby but lets start with the main differerences. 

Javascript is a prototype-based language based on prototypes rather than being class-based like Ruby. A bit about prototypes a bit later. A class based language would have a class and instances which is an instantion of a class. For example, **Cars** could be a class and the individual brands of the cars like **Toyota, BMW, Honda** could be the instance of the Car class. An instance has exactly has all the properties if its parent class. 

In Javascript though, there are no classes and instances. It simply has objects and you define a constructor function to create objects with a particular initial set of properties and values. You use the new operator with a constructor function to create a new object 

![](http://flatironschool.com/wp-content/uploads/tumblr_inline_mwmg1319z31rtan47.png)

The maruCat object is considered a new instance of the Cat prototype. Prototype is essentially the same as Class in Ruby. Note that **this** in JavaScript is the same concept as **self**  in Ruby.



In Ruby's class based object oriented programming and has two distinct entities: classes and instances. A class defines all of the properties that characterize a certain set of objects; while an instance on the other hand, is the instantiation of a class; that is, one of its members. For example, **Toyota** could be an instance of the **Car** class, representing a particular name as a brand of the car class. An instance has exacxtly the same properties of its parent class. (no more, no less).

In Ruby, you define a class in seperate class definitions. In that definitions you can specify special methods called **constructors** to create instances. You use the **new** operator in associations with the costructor method to create class instances. 



Here is a comparison of class-based and prototype-based object language.

**Class-based:**

1. Class and instances are distinct entities.
2. Defines a class with a class keyword; instantiate a class with constructor methods.
3. Inherit properties by following the class chain.
4. Class definition specifies all properties of all instances of a class. Cannot add properties dynamically at run time.


**Prototype-based:**

1. All objects can inherit from another object.
2. Define and create a set of objects with constructor functions.
3. Inherit properties by following the prototype chain.
4. Constructor function or prototype specifies an initial set of properties. Can add or remove properties dynamically to          individual objects or to the entire set of objects.





Here's a fun fact, Javascript was created by Brendan Eich in 10 days in 1995 and was adopted by Microsoft’s Internet Explorer 3.0 in 1996.


