# What is the out keyword in C#?

- The out keyword is used to pass arguments to methods by reference, similar to ref, but with one key difference:

### The variable passed as out doesn’t need to be initialized before being passed, but must be assigned inside the method before the method ends.

- It's commonly used when a method needs to return multiple values.

## Example: Using out to return a value

```
using System;

class Program
{
    static void Main()
    {
        int result;
        CalculateSquare(5, out result); // No need to initialize 'result' before calling

        Console.WriteLine("Square is: " + result);
    }

    static void CalculateSquare(int number, out int square)
    {
        square = number * number; // Must assign before returning
    }
}
```

## Output:

```
Square is: 25
```

### Key Differences: ref vs out

| Feature        | `ref`                          | `out`                          |
| -------------- | ------------------------------ | ------------------------------ |
| Initialization | Must be initialized before use | Doesn't need to be initialized |
| Assignment     | Optional inside method         | Must be assigned inside method |
| Use case       | Modify input value             | Return additional output       |
