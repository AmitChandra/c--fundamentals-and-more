# What is string immutability in C#?

- In C#, strings are immutable, which means:

### Once a string object is created, it cannot be changed. Any operation that appears to modify a string actually creates a new string object in memory.

## Why is string immutability important?

- It makes strings thread-safe and predictable.

- Helps optimize performance through string interning.

- Ensures that once created, strings remain constant and safe from unintended changes.

## Example:

```
using System;

class Program
{
    static void Main()
    {
        string original = "Hello";
        string modified = original.ToUpper();

        Console.WriteLine("Original: " + original); // "Hello"
        Console.WriteLine("Modified: " + modified); // "HELLO"
    }
}
```

## Output:

```
Original: Hello
Modified: HELLO
```

- Even though we called .ToUpper() on original, the original string remains unchanged — a new string ("HELLO") was created and assigned to modified.

## Another example: Concatenation creates a new string

```
string a = "Hello";
a += " World"; // Creates a new string and assigns it back to 'a'
```

### Even though it looks like a was modified, under the hood:

- A new string "Hello World" is created.

- The old "Hello" is discarded (and collected by the garbage collector).

## How to handle performance issues from immutability?

- If you’re doing many string manipulations, use StringBuilder:

```
using System.Text;

StringBuilder sb = new StringBuilder();
sb.Append("Hello");
sb.Append(" World");

Console.WriteLine(sb.ToString()); // Output: Hello World
```

- StringBuilder is mutable, so it's more efficient for repeated modifications.

## Summary:

- Strings are immutable: once created, they can't be changed.

- Any "modification" creates a new string object.

- Use StringBuilder for heavy string manipulation.

## ✅ Summary:

| Feature                            | Immutable `string` | Mutable `StringBuilder` |
| ---------------------------------- | ------------------ | ----------------------- |
| Modifiable?                        | ❌ No              | ✅ Yes                  |
| Memory efficient for many changes? | ❌ No              | ✅ Yes                  |
| Safe for concurrent use?           | ✅ Yes             | ⚠️ Only with care       |
| Stored in string pool (interning)? | ✅ Yes             | ❌ No                   |
