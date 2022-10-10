---
title: Interfaces
parent: Object Oriented Programming
nav_order: 5
description: A C# interface contains only the signatures of methods. A class that inherits from the interface must implement the members of the interface.
---

# Interfaces

An interface contains only the signatures of methods. A class that inherits from the interface must implement the members of the interface.

****

The following code illustrates an interface.

```csharp
using System;

namespace LearnCSharp
{
    class Program
    {
        static void Main(string[] args)
        {
            IShape myRectangle = new Rectangle(4, 2);
            int area = myRectangle.Area();

            Console.WriteLine($"The area of the rectangle is {area}");
        }
    }
}

public interface IShape
{
    int Area();
}

public class Rectangle : IShape
{
    public int Length { get; set; }
    public int Breadth { get; set; }

    public Rectangle(int length, int breadth)
    {
        Length = length;
        Breadth = breadth;
    }

    public int Area()
    {
        return Length * Breadth;
    }
}
```

```
The area of the rectangle is 8
```

IShape is an interface that has a method signature named Area that should return an integer. 

The class Rectangle inherits from the IShape interface and therefore must implement a method named Area. 

The Rectangle class has Length and Breadth properties and a constructor to initialize these properties, in addition, it has an implementation for the Area() method as shown in the code above.

## Using an interface in a constructor

The following example illustrates how we can use an interface in a constructor of a class.

```csharp
using System;

namespace LearnCSharp
{
    class Program
    {
        static void Main(string[] args)
        {
            IShape myRectangle = new Rectangle(4, 2);
            Solid myCuboid = new Solid(myRectangle, 3);
            int volume = myCuboid.CalculateVolume();

            Console.WriteLine($"The volume of the cuboid is {volume}");
        }
    }
}

public interface IShape
{
    int Area();
}

public class Rectangle : IShape
{
    public int Length { get; set; }
    public int Breadth { get; set; }

    public Rectangle(int length, int breadth)
    {
        Length = length;
        Breadth = breadth;
    }

    public int Area()
    {
        return Length * Breadth;
    }
}

public class Solid
{
    public IShape Shape { get; set; }
    public int Height { get; set; }

    public Solid(IShape shape, int height)
    {
        Shape = shape;
        Height = height;
    }

    public int CalculateVolume()
    {
        return Shape.Area() * Height;
    }
}
```

The Solid class has a property called Height. It also has a property named Shape of type IShape (interface). 

Since IShape has a method for Area, we could use that in the Solid class to define a method to calculate the Volume , i.e. Shape.Area() * Height.
