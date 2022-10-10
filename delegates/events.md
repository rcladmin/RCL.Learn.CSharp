---
title: Events
parent: Delegates
nav_order: 2
description: Events in C#.
---

# Introduction

Events enable a class or object to notify other classes or objects when something of interest occurs. The class that sends (or raises) the event is called the publisher and the classes that receive (or handle) the event are called subscribers.

# Delegate

All events are based on the EventHandler delegate, which is defined as follows:

```csharp
public delegate void EventHandler(object sender, EventArgs e);
```

# Steps in setting up an event

1. Publish the the event
2. Add a method for event invocation
3. Raise the event
4. Subscribe to the event
5. Add a method to handle the event

# Publishing an event

Consider the following ``Car`` class that publishes and event

```csharp
public class Car
    {
        public int Speed { get; set; } = 0;
        
        // 1. Publish an event
        public event EventHandler SpeedLimitReached;

        public Car(int speed)
        {
            Speed = speed;
        }

        public void Accelerate(int amount)
        {
            Speed = Speed + amount;

            // 3. Raise the event
            if(Speed > 50)
            {
                OnLimitReached(new EventArgs());
            }
        }

        // 2. Method to invoke the event
        public virtual void OnLimitReached(EventArgs e)
        {
            EventHandler handler = SpeedLimitReached;
            handler?.Invoke(this, e);
        }
    }
```

1. The ``EventHandler`` delegate is used to publish an event named 'SpeedLimitReached' 

2. A method named OnLimitReached is used for the event invocation. It must meet the signature requirements for the ``EventHandler`` delegate, ie returns a void and take an ``EventArgs`` argument

3. When the speed of the car reaches above 50, the event is raised

# Subscribing to an event

Consider the following console app :

```csharp
public class Program
    {
        static void Main(string[] args)
        {
            Car car = new Car(30);

            // 4. Subscribe to the event
            car.SpeedLimitReached += HandleSpeedLimitReached;

            Console.WriteLine("Car is accelerating ..");

            car.Accelerate(30);

        }

        // 5. Method to handle the event
        public static void HandleSpeedLimitReached(object sender, EventArgs e)
        {
            Console.WriteLine("Speed limit reached, time to slow down!");
        }
    }
```

```bash
Car is accelerating ..
Speed limit reached, time to slow down!
```

4. Subscribe to the event by specifying a handler

5. The method ``HandleSpeedLimitReached`` is used to handle the event. It must satisfy the signature for the ``EventHandler`` delegate. When the speed limit is reached, it raises a message in the console window

