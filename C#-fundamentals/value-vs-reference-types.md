# 📚 Value Types vs Reference Types in C#

## 🔹 Value Types

- Stored directly in the stack memory.

- When you assign a value type to a new variable, it copies the value.

- Changing one variable does not affect the other.

- Examples: int, float, bool, char, struct, enum

### Example:

```
int a = 10;
int b = a; // b gets a copy of a

b = 20;

Console.WriteLine(a); // Output: 10 (still 10, not affected by b)
Console.WriteLine(b); // Output: 20

```

- ✅ Key Point: Value types are independent copies.

## 🔹 Reference Types

- Stored in heap memory, but variables hold a reference (address) to that memory.

- When you assign a reference type to another variable, they both point to the same object.

- Changing one variable affects the other.

- Examples: class, string, array, object, delegate

### Example:

```
class Person
{
    public string Name;
}

Person p1 = new Person();
p1.Name = "Alice";

Person p2 = p1; // p2 points to the same Person as p1

p2.Name = "Bob";

Console.WriteLine(p1.Name); // Output: Bob (changed through p2)
Console.WriteLine(p2.Name); // Output: Bob
```

- ✅ Key Point: Reference types share the same memory unless you explicitly create a new object.

# 🧠 Quick Memory Visualization

| Type            | Stored Where | Behavior           |
| --------------- | ------------ | ------------------ |
| Value Types     | Stack        | Independent copies |
| Reference Types | Heap + Stack | Shared references  |

# 🚀 Bonus: Common Mistake to Watch Out For

- Strings behave a little differently — even though they are reference types, they are immutable (can't change their content), so it often feels like a value type.

### Example:

```
string s1 = "hello";
string s2 = s1;

s2 = "world";

Console.WriteLine(s1); // Output: hello
Console.WriteLine(s2); // Output: world
```

- (They don’t affect each other because a new string is created.)

# ✨ In short:

- Value types = copy of data ✅

- Reference types = copy of the reference 🔗
