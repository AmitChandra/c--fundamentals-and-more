# What is the readonly keyword in C#?

- The readonly keyword in C# is used to declare fields that can only be assigned a value during declaration or in a constructor — meaning their value can be set at runtime, but cannot be changed afterward.

## It's commonly used when you want a value to be immutable after object construction, but not necessarily known at compile time (unlike const).

### Syntax:

```
readonly dataType variableName;
```

## Example:

```
using System;

class Car
{
    public readonly string Model;

    public Car(string model)
    {
        Model = model; // Allowed — assigned in constructor
    }

    public void ShowModel()
    {
        Console.WriteLine("Car model: " + Model);
    }
}

class Program
{
    static void Main()
    {
        Car myCar = new Car("Toyota");
        myCar.ShowModel();

        // myCar.Model = "Honda"; // ❌ Error: Cannot assign to 'Model' because it is readonly
    }
}
```

## Output:

```
Car model: Toyota
```

## Key Differences: const vs readonly

| Feature       | `const`                         | `readonly`                            |
| ------------- | ------------------------------- | ------------------------------------- |
| Value set at  | **Compile time**                | **Runtime (in constructor)**          |
| Can assign in | Declaration only                | Declaration **or** constructor        |
| Allowed types | Primitives, `string`, constants | Any type (even objects, structs)      |
| Static?       | Implicitly `static`             | Not static unless explicitly declared |

## Example: Both **const** and **readonly** in one class

```
class Config
{
    public const int MaxUsers = 100;              // Known at compile time
    public readonly DateTime CreatedAt;           // Known only at runtime

    public Config()
    {
        CreatedAt = DateTime.Now; // Allowed
    }
}
```

## Summary:

- Use **const** when the value is truly constant and never changes.

- Use **readonly** when the value should be set once at runtime (e.g., during object creation) and not modified after.
