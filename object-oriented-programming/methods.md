---
title: Methods
parent: Object Oriented Programming
nav_order: 3
description: A C# method carries out a function within a class.
---

# Methods

A method carries out a function within a class.

****

The following code illustrates a method.

```csharp
using System;

namespace LearnCSharp
{
    class Program
    {
        static void Main(string[] args)
        {
            Square mySquare = new Square(4);
            int area = mySquare.CalculateArea();

            Console.WriteLine($"The area of a square with side {mySquare.Side} is {area}");
        }
    }
}

public class Square
{
    public Square(int side)
    {
        Side = side;
    }

    public int Side { get; set; }

    public int CalculateArea()
    {
        return Side * Side;
    }
}
```

```
The area of a square with side 4 is 16
```

In the Square class, we have a method named CalculateArea(), this method does not take any arguments. 

The method uses the Side property to calculate the area of the square. The method returns an integer value for the area (Side * Side).

## Method Overloads

A class can have two or more methods with the same name but take different number and types of arguments and carry out functions differently. This is called method overloading.

```csharp
using System;

namespace LearnCSharp
{
    class Program
    {
        static void Main(string[] args)
        {
            Shape myCircle = new Shape();
            int radius = 2;
            decimal areaCircle = myCircle.CalculateArea(radius);

            Shape myRectangle = new Shape();
            int length = 4;
            int breadth = 2;
            int areaRectangle = myRectangle.CalculateArea(length, breadth);

            Console.WriteLine($"The area of a circle with radius {radius} is {areaCircle}");
            Console.WriteLine($"The area of a rectangle with length {length} and breadth {breadth} is {areaRectangle}");
        }
    }
}

public class Shape
{
    public decimal CalculateArea(int Radius)
    {
        return 3.14M * Radius * Radius;
    }

    public int CalculateArea(int Length, int Breadth)
    {
        return Length * Breadth;
    }
}
```

```
The area of a circle with radius 2 is 12.56
The area of a rectangle with length 4 and breadth 2 is 8
```

In the Shape class, there are two methods called CalculateArea , but one calculates the a area of a circle and the other calculates the area of a rectangle. 

The first method takes one argument, of type integer, for the radius and returns an area, of type decimal, for the circle (in, 3.14M, M shows that this is a decimal number). 

The second method takes two arguments, of type integer, for the length and breadth and returns the area, of type integer, for the rectangle. 

The CalculateArea() method has two overloads.
