---
title: Types
has_children: false
nav_order: 3
description: C# types
---

# Types
C# is a strongly typed language. Every variable must be defined by a type. 

****

The following is a list of common types used in C#:

- string
- int
- long
- decimal
- double
- bool
- DateTime

## Strings

The **string** type is used for text. The following code shows an example of use of the string variable.

```csharp
string name = "Anil";
Console.WriteLine($"Hello {name}");
```

**Output**
```
Hello Anil
```

## Integers

Integers (**int**) are used to represent whole numbers (e.g. 3, 5, etc.). The range for the int type is :  -2,147,483,648 to 2,147,483,647.

The **long** type has a greater range : -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807

```csharp
int x = 1;
int y = 3;
int sum = x + y;
Console.WriteLine($"Sum : {sum.ToString()}");
```

**Output**
```
Sum : 4
```

## Decimal

The type : **Decimal** is used to represent decimal numbers (eg: 3.14) with a *fixed number of decimal places*. Note the letter 'M' to represent a decimal.

```csharp
Decimal pi = 3.14M;
Console.WriteLine($"The value of pi is {pi}");
```

**Output**
```
The value of pi is 3.14
```

## Double

The type : **double** is used to represent floating point numbers. Doubles require less memory than decimals but are less precise.

```csharp
Double pi = 3.14159;
Console.WriteLine($"The value of pi is {pi}");
```

**Output**
```
The value of pi is 3.14159
```

## Bool

The type : **bool** is used to represent true or false(Boolean) values.

```csharp
bool b = true;
Console.WriteLine($"{b.ToString()}");
```

**Output**
```
True
```

## DateTime

The type: **DateTime** is used to represent Date and Time.

```csharp
DateTime now = DateTime.Now;
Console.WriteLine($"The current date and time is {now}");
```

**Output**
```
The current date and time is 1/27/2020 4:27:54 PM
```

## Arrays

You can store multiple variables of the same type in an array data structure. You declare an array by specifying the type of its elements. Note the index starts from 0.

```csharp
int[] numbers = { 3, 0, 4, 8, 2 };
int a = numbers[3];
Console.WriteLine($"The fourth number in the array is : {a.ToString()}");
```

**Output**
```
The fourth number in the array is : 8
```
