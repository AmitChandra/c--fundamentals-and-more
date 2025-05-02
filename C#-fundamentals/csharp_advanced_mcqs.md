# C# Advanced MCQs: Core Language Features

### 1. What is "boxing" in C#?

- [ ] Converting a reference type to a value type
- [x] Converting a value type to a reference type
- [ ] Copying a value to another variable
- [ ] Creating an object from a string

### 2. What is "unboxing" in C#?

- [ ] Converting a class to a struct
- [x] Extracting the value type from the object
- [ ] Casting one reference type to another
- [ ] Removing a variable from memory

### 3. Which keyword is used to pass arguments by reference?

- [ ] `out`
- [ ] `in`
- [x] `ref`
- [ ] `var`

### 4. Which statement about `out` parameters is correct?

- [ ] They must be assigned before being passed.
- [x] They must be assigned within the method before it returns.
- [ ] They are read-only inside the method.
- [ ] They can't be used in static methods.

### 5. Which statement about `in` parameters is correct?

- [ ] They can be modified inside the method.
- [x] They are passed by reference but are read-only.
- [ ] They are passed by value.
- [ ] They require initialization inside the method.

### 6. What is the difference between `const` and `readonly`?

- [ ] `const` is evaluated at runtime, `readonly` at compile time
- [x] `const` is compile-time constant, `readonly` can be assigned at runtime (in constructor)
- [ ] Both are evaluated at runtime
- [ ] No difference

### 7. Which of the following is a valid `readonly` declaration?

```csharp
readonly int x = 10;
```

- [ ] Only valid inside a method
- [x] Valid as a field inside a class
- [ ] Invalid syntax
- [ ] Only allowed for static members

### 8. Strings in C# are:

- [ ] Mutable value types
- [ ] Mutable reference types
- [x] Immutable reference types
- [ ] Immutable value types

### 9. What does it mean that strings are immutable in C#?

- [ ] You can change characters in a string
- [x] Once created, the string value cannot be changed
- [ ] Strings are passed by value
- [ ] Strings are stored on the stack

### 10. What is string interning in C#?

- [ ] Allocating a new string on the heap
- [ ] Cloning a string for memory safety
- [x] Reusing identical string literals to save memory
- [ ] Storing string variables in global memory

### 11. Which of the following types is a value type?

- [x] `int`
- [ ] `string`
- [ ] `class`
- [ ] `delegate`

### 12. What happens when you assign one reference type to another?

- [ ] A copy of the data is made
- [x] Both variables point to the same object
- [ ] Compilation error
- [ ] A shallow copy is made

### 13. Which is true about passing a variable using `ref`?

- [ ] The method must assign the variable
- [x] The variable must be initialized before passing
- [ ] It creates a new reference
- [ ] It behaves like `in`
