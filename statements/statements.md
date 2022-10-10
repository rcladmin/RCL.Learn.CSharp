---
title: Statements
has_children: false
nav_order: 4
description: Statements in C# are used to change the flow of your code logic.
---

# Statements

Statements are used to change the flow of your code logic. 

****

Some of the most popular statements used in C# are :
- if – else
- do - while
- for
- foreach

## if - else

An **if** statement identifies which statement to run based on the value of a Boolean (true or false) condition. 

The following are some common comparators that can be used when you set up conditions:

- if(a == b) : if a is equal to b;
- if(a < b) : if a is less than b;
- if(a > b) : if a is greater than b;
- if(a != b) : if a is not equal to b;

```csharp
string result = string.Empty;
int number = 5;
if (number == 12)
{
    result = "dozen";
}
else
{
    result = "not a dozen";
}

Console.WriteLine($"The amount {number.ToString()} is {result}");
```

**Output**
```
The amount 5 is not a dozen
```

## do - while

The **do** statement executes a statement repeatedly until a specified expression evaluates to false. 

```csharp
int sum = 0;
int i = 1;
do
{
    sum = sum + i;
    i++;
}
while (i < 11);

Console.WriteLine($"The sum of the numbers 1 to 10 is : {sum}");
```

**Output**
```
The sum of the numbers 1 to 10 is : 55
```

## for loop

By using a **for** loop, you can run a statement repeatedly until a specified expression evaluates to false. 

```csharp
int sum = 0;
for (int i = 1; i < 11; i++)
{
    sum = sum + i;
}

Console.WriteLine($"The sum of the numbers 1 to 10 is : {sum}");
```

**Output**
```
The sum of the numbers 1 to 10 is : 55
```

## foreach loop

The foreach statement repeats statement(s) for each element in an array. 

```csharp
string[] names = { "Jane", "Sue", "Lisa", "Mary" };
foreach (string item in names)
{
    if (item == "Mary")
    {
        Console.WriteLine("Hey, Mary was found !");
    }
    else
    {
        Console.WriteLine("Looking for Mary ...");
    }
}
```

**Output**
```
Looking for Mary ...
Looking for Mary ...
Looking for Mary ...
Hey, Mary was found !
```
