+++
date = "2018-07-10T00:00:00"
draft = false
tags = ["Coding", "C-Sharp"]
title = "Object Oriented C# - (Polymorphism, Interface & Abstract Class"
math = false
summary = """
An **Interface** is a contract: The person writing the interface says, "hey, I accept things looking that way", and the person using the interface says "OK, the class I write looks that way".

An interface is an empty shell. There are only the signatures of the methods, which implies that the methods do not have a body. The interface can't do anything. It's just a pattern.

**Abstract classes** look a lot like interfaces, but they have something more, **You can define a behavior for them**. It's more about a person saying, "these classes should look like that, and they have that in common, so fill in the blanks!".

"""

[header]
image = "headers/oop.jpg"
caption = "Image credit: [pexels](www.pexels.com)"

+++
## Overview

In this post I will discuss about

 1. Polymorphism  
 2. Interface
 3. Abstract Class 
 
**Polymorphism**

> Polymorphism =Poly + morphism = Multiple + forms.

![Imgur](https://i.imgur.com/3Bf7vcg.jpg)

***Polymorphism can be achieved by method overriding and also by virtual method***

→ What is method overriding ? 

- Method overriding means changing the implementation of an Inherited method.

- If a declare a method as virtual in the base class, we can override it in a derived class.


```
public class Shape
{
 public virtual Draw()
 {
 // Default implementation for all derived classes
 }
}

public class Circle : Shape
{
 public override Draw()
 {
 // Changed implementation
 }
}
public class Rectangle : Shape
{
  public override Draw()
  {
    // change implementation
  }
}

```

**Interface**

→ Interface is type of which is contain property, method that has no implementation. An interface is simply a declaration of the capabilities (or services) that a class should provide.

- Naming convention of interface name starts with a Capital I
 
- No implementation 

- An interface can only declare methods and properties, but not fields (because fields are about implementation detail).

- No access modifier (private, public) 

```

public interface ITaxCalculator 
{
    // int Tax;	
    int Tax {get; set;}
    int calculate(); // no implementation and no access modifier 
}

```

***Why use Interface ?***

→ Flexibility in implementation 

→ Interfaces are better suited to situations in which your applications require many possibly unrelated object types to provide certain functionality.

→ you can use multiple implementation of a same Interface. 

→ Interfaces help building loosely coupled applications. We reduce the coupling between
two classes by putting an interface between them. This way, if one of these classes
changes, it will have no impact on the class that is dependent on that (as long as the
interface is kept the same)

***Benefit of using Interface***

→ we can use interface to change our application behaviour by extending its code, rather than changing existing code.

→ Different implementation of that interface at runtime (kind of polymorphism) 


***Interfaces and Inheritance***

→ One of the common misconceptions about interfaces is that they are used to
implement multiple inheritance in C#. This is fundamentally wrong, yet many books
and videos make such a false claim.

→  With inheritance, we write code once and reuse it without the need to type all that
code again.

→  With interfaces, we simply declare the methods and properties the implementing class should contain. Then we need to type all that declaration along with the actual implementation in that class. So, code is not inherited, even the declaration of the members!


***Abstract Class***

Abstract modifier states that a class or a member __misses implementation__. We use abstract members when it doesn’t make sense to implement them in a base class. When a class member is declared as abstract, that class needs to be declared as abstract as well. That means that class is not complete. In derived classes, we must need to override (implement) the abstract members in the base class.

```
public abstract class Shape
{
	int area;
	
	// define behavior, implement this for everybody
	int GetArea()
	{
		return this.area;
	}
	
// That can be very different, force them to provide their own implementation.
  public abstract void Draw(); 
}

public class Circle : Shape
{
  public override void Draw()
  {
    // implementation for circle 
  }
}
```

>It is impossible to define Shape because the concept of shape is abstract (hide the essential details, shows only the features or in other word the outside view).

***Difference Between Interface and Abstract Class***

An **Interface** is a contract: The person writing the interface says, "hey, I accept things looking that way", and the person using the interface says "OK, the class I write looks that way".

An interface is an empty shell. There are only the signatures of the methods, which implies that the methods do not have a body. The interface can't do anything. It's just a pattern.

----------
**Abstract classes** look a lot like interfaces, but they have something more, **You can define a behavior for them**. It's more about a person saying, "these classes should look like that, and they have that in common, so fill in the blanks!".

------------------


follow me on [facebook](https://www.facebook.com/shohan4556) 

follow me on [twitter](https://www.twitter.com/shohan4556) 

follow me on [github](https://www.github.com/shohan4556) 


