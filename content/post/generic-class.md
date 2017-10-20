+++
date = "2017-01-01T00:00:00"
draft = false
tags = ["Coding", "C-Sharp"]
title = "Intermediate C# - Generic Class"
math = false
summary = """
Generic class same as typical class in C# except Generic type. So what the f**k is generic type ? Generic type means it is not
"""

[header]
image = "headers/cover-image-1.jpg"
caption = "Image credit: [**pixabay**](https://pixabay.com/en/hacker-internet-technology-1569744/)"

+++

Generic class same as typical class in C# except Generic type. So what the f**k is generic type ? Generic type means it is not specified any particular **type**. 
Let's see an example of an ordinary class 

    class MyOrdinaryClass{
	    // properties and methods goes here
    }
	   
    var myObj1 = new MyOrdinaryClass();
So what we did here, we have instantiated an object **myObj1** type of **MyOrdinaryClass**. 

Here is an example of generic class 


    class MyGenericClass <T> {
	    // properties and methods goes here, no special same as ordinary class 
    }
    
       var myObj2 = new MyGenericClass<int> ();
       var myObj3 = new MyGenericClass<string> ();
   
> There must be a `<T>` after the name of generic class, this is how you have to define generic class. 

   Look at this example, we have instantiate the same class but **with different type (integer and string)** 

> So In simple term Generic class allow you to write class that can work
> with any data type.

The most common use of generic class is **List** 
Here is another example 

     var obj1 = new MyGenericClass<int> ();
     var obj2 = new MyGenericClass<string> ();

     var Gobj1  = new List<string> ();
     var Gobj2 = new List<int> ();
   sample program to follow : 
   

        namespace GenericClass {
    
        class MyGenericClass <T> {
            public void sayHello ( ) {
                Console.WriteLine ("Hello World");
            }
        }
    
    
        class Program {
            static void Main ( string[] args ) {
    
                var myObj2 = new MyGenericClass<int> ();
                var myObj3 = new MyGenericClass<string> ();
    
                myObj2.sayHello ();
                myObj3.sayHello ();
    
                var obj1 = new MyGenericClass<int> ();
                var obj2 = new MyGenericClass<string> ();
    
                var Gobj1  = new List<string> ();
                var Gobj2 = new List<int> ();
    
    
                Console.ReadKey ();
    
            }
        }
    }





	
	

Advantages of using Generic Class :



		1. Reusing same class multiple times 
		
		2. Performance 
		
		3. Type Safety 


----------


follow me on [facebook](https://www.facebook.com/shohan4556) 

follow me on [twitter](https://www.twitter.com/shohan4556)
 
follow me on [github](https://www.github.com/shohan4556) 