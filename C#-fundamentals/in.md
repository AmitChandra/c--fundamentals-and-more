# What is the in keyword in C#?

- The in keyword in C# is used to pass arguments by reference, but as read-only. That means:

### The called method can read the value, but cannot modify it.

- It was introduced in C# 7.2, primarily to optimize performance when passing large value types (like large structs) without copying them, while still protecting them from modification.

## Key Characteristics of in:

- Passed by reference (no copying for large structs).

- Cannot be modified inside the method.

- Useful for performance + immutability.

### Example: Using in parameter

```
using System;

struct Point
{
    public int X;
    public int Y;

    public Point(int x, int y)
    {
        X = x;
        Y = y;
    }

    public void Print()
    {
        Console.WriteLine($"Point: ({X}, {Y})");
    }
}

class Program
{
    static void Main()
    {
        Point p = new Point(3, 4);
        DisplayPoint(in p); // Passed by reference, but read-only
    }

    static void DisplayPoint(in Point point)
    {
        point.Print();

        // point.X = 10; // ❌ Compile-time error: Cannot assign to 'X' because it is a readonly variable
    }
}
```

# Comparison: ref, out, in

| Keyword | Direction           | Must be initialized before call | Must be assigned in method | Can modify inside method? |
| ------- | ------------------- | ------------------------------- | -------------------------- | ------------------------- |
| `ref`   | In/Out (read-write) | ✅ Yes                          | ❌ No                      | ✅ Yes                    |
| `out`   | Out only            | ❌ No                           | ✅ Yes                     | ✅ Yes                    |
| `in`    | In only (read-only) | ✅ Yes                          | ❌ No                      | ❌ No                     |
