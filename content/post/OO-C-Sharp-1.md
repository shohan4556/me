+++
date = "2018-07-09T00:00:00"
draft = false
tags = ["Coding", "C-Sharp"]
title = "Object Oriented C# - 01"
math = false
summary = """
Having said all that, it doesn’t mean inheritance should be avoided at all times. In fact,
it’s great to use inheritance when dealing with very stable classes on top of small
hierarchies. As the hierarchy grows (or variations of classes increase), the hierarchy,
however, becomes fragile. And that’s where composition can give you a better design.
"""

[header]
image = "headers/oop.jpg"
caption = "Image credit: [pexels](www.pexels.com)"

+++
## Overview

Today we will learn the OOP concept of C#.

 1. Class  
 2. Inheritance 
 3. Composition 
 

**Class**
![Imgur](https://i.imgur.com/1jdDF53.png)

Class is a template or blueprint of an object, it contain variables and method (behaviour). Class encapsulate date (stored in field and behaviour). Object is an instance of a class. Class don't allocate memory, object does.

**Constructor**

A constructor is a method that is called when an instance of a class is created.

- We use constructors to put an object in an early state.

- As a best practice, define a constructor only when an object “needs” to be initialised or it won’t be able to do its job.

- Constructors do not have a return type, not even void, and they should have the exact same name as the class.

```
public class Car {
  
  public string Color;
  public string manufacturer;

// constructor
  public Car(string _color, string _manufacturer){
    Color = _color;
    manufacturer = _manufacturer;
  }

  public void Drive(){
    // car can drive
  }
}
```

**Property**

→ A property is a kind of class member that is used for providing access to fields of a class

→ A property encapsulates a get and a set method.

```
public class Car {
  
  private string _color;
  public string Manufacturer { get; set; }
   
  public string Color
  {
    get{ return _color; }
    set { _color = value; }
  }

  public void Drive(){
    // car can drive
  }
}
```

**Inheritance**

![Imgur](https://i.imgur.com/zmzABEd.jpg)

→ A kind of relationship between two classes that allows one to inherit code from the other class.

→ Is-A relationship.

→ Code reusability is the major benifit of using Inheritance.

→ Example :  A car is a vehicle. (parent class vehicle, child class car).


```
Public class Vehicle{
	// share common attribute 
}

Public class speedBoat : Vehicle{
	// code specific to speedBoat
}
```

**Composition**

![Imgur](https://i.imgur.com/p07mUw0.png)

> Gold fish dont walk

→ Composition is just like Inheritance, another kind of relationship between two classes that allows one to contain other.

→ Has-a relationship

→ Example : Car/Speedboat has an engine. 


```
public class Car{
   public string name;
// has an engine 
}

public class SpeedBoat{
  
  private Engine engine;
  
// constructor
  public speedBoat(Engine _engine){
    engine = _engine;
  }

  public void Drive(){
    engine.StartEngine(); // from Engine class 
    Console.WriteLine("Driving speed boat");
  }
}


public class Engine(){
  public void StartEngine(){
      Console.WriteLine("Engine Started");
  }
}

 // form main class
  SpeedBoat myboat = new SpeedBoat(new Engine()); // composition
```

***Problems with inheritance***

• Easily abused by amateur designers / developers

• Leads to large complex/large hierarchies

• Such hierarchies are very fragile and a change may affect many classes

• Results in tight coupling

***Benefits of composition***

• Flexible

• Leads to loose coupling

>Having said all that, it doesn’t mean inheritance should be avoided at all times. In fact,
it’s great to use inheritance when dealing with very stable classes on top of small
hierarchies. As the hierarchy grows (or variations of classes increase), the hierarchy,
however, becomes fragile. And that’s where composition can give you a better design.


----------


follow me on [facebook](https://www.facebook.com/shohan4556) 

follow me on [twitter](https://www.twitter.com/shohan4556) 

follow me on [github](https://www.github.com/shohan4556) 


