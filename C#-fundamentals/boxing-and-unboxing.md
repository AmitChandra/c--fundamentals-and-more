# 📦 Boxing and Unboxing in C#

## 🔹 What is Boxing?

- Boxing is the process of converting a value type into an object (reference type).

- The value type is wrapped inside a System.Object and stored in the heap memory.

- Automatic when you assign a value type to an object variable.

### Example:

```
int num = 123;           // Value type
object obj = num;        // Boxing: num is boxed into an object
```

- Now obj holds a reference to the boxed value of num.

- ✅ Key Point: Boxing is implicit — you don't need to write any special code.

## 🔹 What is Unboxing?

- Unboxing is the process of extracting the value type from the object.

- You take the boxed object and cast it back to its original value type.

- You must manually cast it.

### Example:

```
object obj = 123;         // Boxing
int num = (int)obj;       // Unboxing: cast object back to int
```

- ✅ Key Point: Unboxing is explicit — you must cast the object.

## 🧠 Important Points

| Boxing                                       | Unboxing                                  |
| -------------------------------------------- | ----------------------------------------- |
| Value type ➔ Object                          | Object ➔ Value type                       |
| Happens automatically                        | Happens manually (explicit cast)          |
| Allocates memory on heap                     | Need correct type casting                 |
| May cause performance hit if done frequently | If wrong type during unboxing ➔ Exception |

# 🚨 Example with Danger (Invalid Unboxing)

```
object obj = 123;      // Boxing

// Wrong unboxing
string str = (string)obj;  // ❌ Error: InvalidCastException

```

# 🚀 Why Does Boxing/Unboxing Matter?

- Performance: Boxing creates a new object in heap memory — it’s slower and causes GC (Garbage Collection) pressure.

- Best practice: Avoid excessive boxing/unboxing in performance-critical code.

- Generics in C# (List<T>, etc.) were introduced partly to avoid boxing/unboxing for value types!

# 🔥 Quick Code Summary

```
int num = 10;            // Value type
object boxed = num;      // Boxing
int unboxed = (int)boxed; // Unboxing
```

# 🎯 Example: Using ArrayList (causes boxing/unboxing)

- Before generics, people often used ArrayList to store items of any type.

```
using System;
using System.Collections;

class Program
{
    static void Main()
    {
        ArrayList list = new ArrayList();  // Non-generic list

        int num = 100;

        list.Add(num);   // 👈 Boxing happens here

        int retrieved = (int)list[0]; // 👈 Unboxing happens here

        Console.WriteLine(retrieved); // Output: 100
    }
}
```

## What’s happening here:

- list.Add(num) → num (int, a value type) is boxed into an object.

- list[0] → Returns an object, so you have to unbox it back to int.

### 👉 Problem:

- Boxing/unboxing costs performance (especially in loops or large collections).

- Also, risk of runtime errors if the wrong type is cast!

# ✅ Better Way: Using List<int> (no boxing/unboxing)

- After generics were introduced (List<T>), things became much better!

```
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<int> list = new List<int>();  // Generic list

        int num = 100;

        list.Add(num);   // ✅ No boxing

        int retrieved = list[0]; // ✅ No unboxing needed

        Console.WriteLine(retrieved); // Output: 100
    }
}
```

### What’s happening here:

- List<int> directly stores int values — no boxing or unboxing.

- Safer and faster.

# ✨ Key Takeaway:

| Feature         | ArrayList  | List<int>  |
| --------------- | ---------- | ---------- |
| Type Safety     | ❌ No      | ✅ Yes     |
| Boxing/Unboxing | ❌ Happens | ✅ Avoided |
| Performance     | ❌ Slower  | ✅ Faster  |

# 🔥 Quick Tip

- Always prefer List<T> over ArrayList (or any generics) when working with value types like int, float, etc.

- This avoids hidden performance issues caused by boxing/unboxing.
