# C# Programming Questions: Core Language Concepts

### 1. Boxing and Unboxing

**Question:**  
Write a program that demonstrates boxing and unboxing with an `int` variable.

```csharp
int num = 123;
// Box the integer
object obj = num;
// Unbox the integer
int unboxed = (int) obj;
Console.WriteLine(unboxed);
```

---

### 2. Value vs Reference Type

**Question:**  
Write a program to show the difference between value type and reference type assignment.

```csharp
using System;

struct MyStruct
{
    public int Number;
}

class MyClass
{
    public int Number;
}

class Program
{
    static void Main()
    {
        // Value Type
        MyStruct struct1 = new MyStruct { Number = 10 };
        MyStruct struct2 = struct1;
        struct2.Number = 20;

        Console.WriteLine("Value Type:");
        Console.WriteLine($"struct1.Number = {struct1.Number}"); // Output: 10
        Console.WriteLine($"struct2.Number = {struct2.Number}"); // Output: 20

        // Reference Type
        MyClass class1 = new MyClass { Number = 10 };
        MyClass class2 = class1;
        class2.Number = 20;

        Console.WriteLine("\nReference Type:");
        Console.WriteLine($"class1.Number = {class1.Number}"); // Output: 20
        Console.WriteLine($"class2.Number = {class2.Number}"); // Output: 20
    }
}

```

---

### 3. `ref` Keyword

**Question:**  
Write a method that doubles the value of a number using the `ref` keyword and call it from `Main`.

```csharp
using System;

class Program
{
    // Method that doubles the value using ref
    static void Double(ref int number)
    {
        number *= 2;
    }

    static void Main()
    {
        int value = 5;
        Console.WriteLine("Before: " + value);

        // Call method with ref
        Double(ref value);

        Console.WriteLine("After: " + value); // Output: 10
    }
}

```

---

### 4. `out` Keyword

**Question:**  
Write a method that returns multiple values using the `out` keyword.

```csharp
using System;

class Program
{
    // Method that returns two values using out parameters
    static void GetCoordinates(out int x, out int y)
    {
        x = 10;
        y = 20;
    }

    static void Main()
    {
        int a, b;
        GetCoordinates(out a, out b);

        Console.WriteLine($"X: {a}, Y: {b}"); // Output: X: 10, Y: 20
    }
}

```

---

### 5. `in` Keyword

**Question:**  
Write a method that takes a large struct as an `in` parameter to avoid unnecessary copying.

```csharp
using System;

readonly struct LargeStruct
{
    public int A, B, C, D, E, F;

    public LargeStruct(int a, int b, int c, int d, int e, int f)
    {
        A = a;
        B = b;
        C = c;
        D = d;
        E = e;
        F = f;
    }
}

class Program
{
    // Method accepting a large struct by readonly reference
    static void PrintStruct(in LargeStruct data)
    {
        Console.WriteLine($"A: {data.A}, B: {data.B}, C: {data.C}, D: {data.D}, E: {data.E}, F: {data.F}");
    }

    static void Main()
    {
        LargeStruct ls = new LargeStruct(1, 2, 3, 4, 5, 6);
        PrintStruct(in ls);
    }
}

```

---

### 6. `const` vs `readonly`

**Question:**  
Write a class that uses both `const` and `readonly` fields, and demonstrate their initialization.

```csharp
using System;

class ConstantsDemo
{
    // Compile-time constant
    public const double Pi = 3.14159;

    // Runtime constant - can only be assigned in constructor
    public readonly int Age;

    // Constructor to initialize readonly field
    public ConstantsDemo(int age)
    {
        Age = age;
    }

    public void Display()
    {
        Console.WriteLine($"Pi: {Pi}, Age: {Age}");
    }
}

class Program
{
    static void Main()
    {
        ConstantsDemo demo = new ConstantsDemo(25);
        demo.Display();
    }
}

```

---

### 7. String Immutability

**Question:**  
Write a program that shows how strings are immutable in C#.

```csharp
using System;

class Program
{
    static void Main()
    {
        string str1 = "Hello";
        string str2 = str1;

        // Attempt to modify str1
        str1 = "World";

        // Showing that str2 remains unchanged
        Console.WriteLine($"str1: {str1}"); // Output: World
        Console.WriteLine($"str2: {str2}"); // Output: Hello
    }
}

```

---

### 8. String Interning

**Question:**  
Write a program that demonstrates string interning behavior in C#.

```csharp
using System;

class Program
{
    static void Main()
    {
        // Creating two strings using the same literal
        string str1 = "hello";
        string str2 = "hello";

        // Creating a new string object dynamically and interning it
        string str3 = new string(new char[] { 'h', 'e', 'l', 'l', 'o' });
        str3 = string.Intern(str3); // Explicitly intern the string

        // Check if str1 and str2 refer to the same object
        Console.WriteLine($"str1 and str2 are the same object: {object.ReferenceEquals(str1, str2)}"); // True

        // Check if str1 and str3 refer to the same object
        Console.WriteLine($"str1 and str3 are the same object: {object.ReferenceEquals(str1, str3)}"); // True
    }
}

```

---
