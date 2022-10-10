---
title: Abstract Factory
parent: Design Patterns
nav_order: 4
description: In the C# abstract factory method a factory creates other factories, and these factories in turn create objects derived from interfaces.
---

# Abstract Factory
A factory that creates other factories, and these factories in turn create objects derived from interfaces.

****

The Abstract Factory Method is a frequently used creational design pattern.

```csharp
using System;

namespace LearnCSharp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("What meal do you prefer? (V)egan or (M)eat?");
            char input = Console.ReadKey().KeyChar;
            ICuisineFactory cuisineFactory;
            switch (input)
            {
                case 'V':
                    cuisineFactory = new VegetableDishFactory();
                    break;
                case 'M':
                    cuisineFactory = new MeatDishFactory();
                    break;
                default:
                    throw new NotImplementedException();
            }
            IMeal meal = cuisineFactory.Create();
            Console.WriteLine($"\nI got a {meal.Get()}");
        }
    }
}

// Abstract factory
public interface ICuisineFactory
{
    IMeal Create();
}

// Concrete factory A
public class VegetableDishFactory : ICuisineFactory
{
    public IMeal Create()
    {
        return new VegetableSoup();
    }
}

// Concrete factory B
public class MeatDishFactory : ICuisineFactory
{
    public IMeal Create()
    {
        return new Steak();
    }
}

// Abstract product
public interface IMeal
{
    string Get();
}

// Concrete product A
public class Steak : IMeal
{
    public string Get()
    {
        return "steak";
    }
}

// Concrete product B
public class VegetableSoup : IMeal
{
    public string Get()
    {
        return "vegetable soup";
    }
}
```

```
What meal do you prefer? (V)egan or (M)eat?
M
I got a steak
```

The ICuisineFactory interface is used to create the VegetableDishFactory and the MeatDishFactory.

These factories in turn create objects from the VegetableSoup and Steak classes using the IMeal interface.
