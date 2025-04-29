# What is the ref keyword in C#?

- The ref keyword in C# allows a method to change the value of a variable that was passed into it. Normally, C# passes parameters by value (which means it makes a copy), but ref tells C# to pass the reference instead — meaning both the caller and the method work on the same memory location.

## Example:

```
using System;

class Program
{
    static void Main()
    {
        int number = 10;

        Console.WriteLine("Before method call: " + number);

        DoubleValue(ref number); // Notice 'ref' used when calling

        Console.WriteLine("After method call: " + number);
    }

    static void DoubleValue(ref int x) // Notice 'ref' in method definition
    {
        x = x * 2;
    }
}
```

## Output:

```
Before method call: 10
After method call: 20
```

# Key Points:

- Declaration and call both must use ref.

- The variable must be initialized before passing it as ref.

- Changes made to the parameter inside the method are reflected outside the method too.

## Another example: Swapping two numbers

```
using System;

class Program
{
    static void Main()
    {
        int a = 5, b = 10;

        Console.WriteLine($"Before Swap: a = {a}, b = {b}");

        Swap(ref a, ref b);

        Console.WriteLine($"After Swap: a = {a}, b = {b}");
    }

    static void Swap(ref int x, ref int y)
    {
        int temp = x;
        x = y;
        y = temp;
    }
}
```

## Output:

```
Before Swap: a = 5, b = 10
After Swap: a = 10, b = 5
```

- Here, because ref is used, the Swap method can actually swap the real variables a and b.
