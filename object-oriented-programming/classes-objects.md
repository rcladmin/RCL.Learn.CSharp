---
title: Classes and Objects
parent: Object Oriented Programming
nav_order: 2
description: A C# class is the blueprint from which individual objects are created.
---

# Classes and Objects

Classes and objects form the basis of object oriented programming.

****

## Class

A class is the blueprint from which individual objects are created.

```csharp
namespace LearnCSharp
{
    public class Square
    {
        public int Side { get; set; }
    }
}
```

In the code above, we declare a class called Square. The word 'public' is an accessor, this class can be accessed by other classes. 

In the Square class, we declare a public property named Side that is an integer.

## Object

An object is an instance of a class.

```csharp
using System;

namespace LearnCSharp
{
    class Program
    {
        static void Main(string[] args)
        {
            Square smallSquare = new Square();
            smallSquare.Side = 1;

            Square bigSquare = new Square();
            bigSquare.Side = 600;

            Console.WriteLine($"The length of the Side for the bigSquare is {bigSquare.Side}");
        }
    }
}

public class Square
{
    public int Side { get; set; }
}
```

```
The length of the Side for the bigSquare is 600
```

Above, we have a class named Square. From that class, we instantiate two objects , one called smallSquare and the other called bigSquare. We use the 'new' keyword to instantiate an object. 

We can set the properties of objects by using the dot (.) operator, for instance, we set the Side property of the small square to 1 by writing smallSquare.Side = 1;

If we want to get the property of an object we also use the dot (.) operator. For instance, to get the Side of the bigSquare we write : bigSquare.Side.

## Constructors

Constructors set the initial values of properties when a class in instantiated.

```csharp
using System;

namespace LearnCSharp
{
    class Program
    {
        static void Main(string[] args)
        {
            Square mySquare = new Square(4);

            Console.WriteLine($"The length of the Side for the mySquare object is {mySquare.Side}");
        }
    }
}

public class Square
{
    public int Side { get; set; }

    public Square(int side)
    {
        Side = side;
    }
}
```

```
The length of the Side for the mySquare object is 4
```

In the Square class, we have a constructor. The constructor has the same name as the class. 

The constructor takes an integer parameter named 'side'. When the class is instantiated, the constructor runs first, and sets the Side property to the value (or argument) we provide to the parameter.

We instantiate an object named mySquare and pass in an argument of 4 to the constructor. The constructor, will inturn, set the Side property to 4.
