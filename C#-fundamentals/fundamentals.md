🌟 C# Fundamentals
✨ What is C#?
C# (pronounced "C-Sharp") is a modern, object-oriented programming language.

Developed by Microsoft as part of its .NET platform.

It’s used for building web apps, desktop apps, mobile apps, games (with Unity), and more.

🛠️ Basic Concepts of C#

1. Variables and Data Types
2. Variables store data.

C# is strongly typed, meaning you must specify the data type.

```int age = 25;
string name = "John";
bool isStudent = true;
double price = 19.99;
```

### Common data types:

int, float, double, bool, string, char, decimal

🛠️ Basic Concepts of C#

# 1. Variables and Data Types

- Variables store data.
- C# is strongly typed, meaning you must specify the data type.

```int age = 25;
string name = "John";
bool isStudent = true;
double price = 19.99;
```

# 2. Control Statements

- These let you control the flow of the program:

- If-Else

```if (age > 18)
{
    Console.WriteLine("Adult");
}
else
{
    Console.WriteLine("Minor");
}
```

- Switch

```
switch (day)
{
    case 1:
        Console.WriteLine("Monday");
        break;
    default:
        Console.WriteLine("Other day");
        break;
}
```

- Loops (for, while, foreach)

```
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

# 3. Object-Oriented Programming (OOP)

### C# is heavily based on OOP principles:

- Class: Blueprint for objects.

- Object: Instance of a class.

- Encapsulation: Hiding internal details.

- Inheritance: One class inherits from another.

- Polymorphism: Same method name behaves differently based on context.

- Abstraction: Hiding complexity and showing only important details.

# Example of a simple class:

```
class Car
{
    public string color = "red";
}

Car myCar = new Car();
Console.WriteLine(myCar.color);
```

# 4. Methods (Functions)

- Reusable blocks of code that perform a task.

```
void SayHello()
{
    Console.WriteLine("Hello World!");
}
```

- You can also pass parameters to methods:

```
void Greet(string name)
{
Console.WriteLine($"Hello {name}!");
}
```

# 5. Properties and Fields

    - Fields are variables inside a class.

    - Properties are a way to control access to fields.

```
private string name;

public string Name
{
    get { return name; }
    set { name = value; }
}
```

6. Namespaces

- Organize code into groups.

- Prevent name conflicts.

```
namespace MyApplication
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello Namespace!");
        }
    }
}
```

7. Exception Handling

- Deal with unexpected errors.

```
try
{
   int result = 10 / 0;
}
catch (Exception ex)
{
   Console.WriteLine("Error: " + ex.Message);
}
finally
{
   Console.WriteLine("This always runs.");
}
```

# 🖥️ C# Development Tools

- Visual Studio (most popular IDE for C#)

- Visual Studio Code (lighter, with C# extensions)

- Rider by JetBrains
