---
title: Static Class
parent: Object Oriented Programming
nav_order: 7
description: In static classes, you do not need to instantiate objects.
---

# Static Class

In static classes, you do not need to instantiate objects.

****

The following code illustrates a static class.

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

            int sum = Math.Add(x, y);

            Console.WriteLine($"The sum of {x} and {y} is {sum}");
        }
    }
}

public static class Math
{
    public static int Add(int x, int y)
    {
        return x + y;
    }
}
```

```
The sum of 2 and 6 is 8
```

Math is a static class, we use the keyword static to declare that the class is static. 

There is a static method named Add that adds two numbers. Since we do not need to instantiate an object, we can return the value from the Add() method by simply using : Math.Add(x,y)
