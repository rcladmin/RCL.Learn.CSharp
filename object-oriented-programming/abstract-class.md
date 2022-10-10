---
title: Abstract Class
parent: Object Oriented Programming
nav_order: 6
description: A C# abstract class cannot be instantiated and can contain abstract and non-abstract members. Classes will inherit from an abstract class an extend its capabilities.
---

# Abstract Class

An abstract class cannot be instantiated and can contain abstract and non-abstract members. Classes will inherit from an abstract class an extend its capabilities.

****

The following code illustrates an abstract class.

```csharp
using System;

namespace LearnCSharp
{
    class Program
    {
        static void Main(string[] args)
        {
            int x = 2;
            int y = 6;

            MathBase myAdder = new Adder(x, y);
            int sum = myAdder.Execute();

            MathBase myMultiplier = new Multiplier(x, y);
            int product = myMultiplier.Execute();

            Console.WriteLine($"The sum of {x} and {y} is {sum}");
            Console.WriteLine($"The product of {x} and {y} is {product}");
        }
    }
}

public abstract class MathBase
{
    public int X { get; set; }
    public int Y { get; set; }

    public MathBase(int x, int y)
    {
        X = x;
        Y = y;
    }

    public abstract int Execute();
}

public class Adder : MathBase
{
    public Adder(int x, int y)
        : base(x, y)
    {
    }

    public override int Execute()
    {
        return X + Y;
    }
}

public class Multiplier : MathBase
{
    public Multiplier(int x, int y)
        : base(x, y)
    {
    }

    public override int Execute()
    {
        return X * Y;
    }
}
```

```
The sum of 2 and 6 is 8
The product of 2 and 6 is 12
```

MathBase is an abstract class. The keyword abstract is used to declare an abstract class. The MathBase class has an abstract method named Execute() that can be overridden by a class that inherits from it. 

There are also two non-abstract properties named X and Y, that will be used to represent two numbers. 

The Adder class inherits from the MathBase class and provides an implementation for the Execute() method (it adds Y and Y) by overriding the abstract method. The Adder class has a constructor that initializes the X and Y properties that it inherits from the MathBase class.

The Multiplier class inherits from the MathBase abstract class and multiplies the two numbers.
