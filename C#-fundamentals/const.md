# What is the const keyword in C#?

- The const keyword in C# is used to declare constants — variables whose value is set at compile time and cannot be changed later.

## Once assigned, a const value cannot be modified, and it is implicitly static (shared across all instances of the class).

### Syntax:

```
const dataType variableName = value;
```

# Example:

```
using System;

class Program
{
    // Declare a constant
    const double Pi = 3.14159;

    static void Main()
    {
        int radius = 5;
        double area = Pi * radius * radius;

        Console.WriteLine("Area of circle: " + area);

        // Pi = 3.14; // ❌ Error: The left-hand side of an assignment must be a variable, property or indexer
    }
}
```

### Output:

```
Area of circle: 78.53975
```

## Key Points:

- const fields must be assigned a value at the time of declaration.

- They are immutable — can't be changed after compilation.

- const is implicitly static, so you access it via the class name, not an instance.

- Valid only with primitive types, string, or other constant expressions.

## Example: Accessing a const from another class

```
class Constants
{
    public const string AppName = "MyApp";
}

class Program
{
    static void Main()
    {
        Console.WriteLine(Constants.AppName);
    }
}
```

## Output:

```
MyApp
```

## When not to use const:

- If the value might change in the future (use readonly instead).

- If the value depends on runtime logic or data.
