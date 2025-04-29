# 🔄 What is string interning in C#?

- String interning is a process where identical string literals are stored only once in memory, in a special pool called the intern pool.

### When you create multiple strings with the same literal value, C# stores only one instance of that string in memory (if interning applies), and all variables reference the same object.

## ✅ Benefits:

- Reduces memory usage for repeating strings.

- Makes reference comparison (==, Object.ReferenceEquals) possible and fast for interned strings.

## 📌 Example: Interned strings

```
string str1 = "hello";
string str2 = "hello";

Console.WriteLine(Object.ReferenceEquals(str1, str2)); // True
```

## Why?

- Both str1 and str2 point to the same string object in the intern pool, because "hello" is a **compile-time constant**.

## ⚠️ Non-interned strings (dynamically created)

```
string str1 = "world";
string str2 = new string(new char[] { 'w', 'o', 'r', 'l', 'd' });

Console.WriteLine(Object.ReferenceEquals(str1, str2)); // False
```

### Here:

- str1 is a literal → interned.

- str2 is built at runtime → not interned automatically, so it's a different object in memory.

## 🛠 Forcing interning at runtime

- You can manually intern a string using:

```
string str1 = "example";
string str2 = new string("example".ToCharArray());

string internedStr2 = string.Intern(str2);

Console.WriteLine(Object.ReferenceEquals(str1, internedStr2)); // True
```

## 🔍 How to check if a string is interned?

```
string value = new string("data".ToCharArray());

if (string.IsInterned(value) != null)
{
    Console.WriteLine("Interned!");
}
else
{
    Console.WriteLine("Not interned.");
}
```

## ✅ Summary:

| Behavior                          | Interned? | ReferenceEqual? |
| --------------------------------- | --------- | --------------- |
| Same string literals              | ✅ Yes    | ✅ True         |
| New strings created at runtime    | ❌ No     | ❌ False        |
| Manually interned with `Intern()` | ✅ Yes    | ✅ True         |
