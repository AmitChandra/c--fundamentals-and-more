# C# Interview MCQs: Value Types vs Reference Types

### 1. Which of the following is a value type in C#?
- [ ] `class`
- [ ] `interface`
- [x] `int`
- [ ] `string`

### 2. What happens when a value type is assigned to another value type variable?
- [x] A copy of the value is made.
- [ ] A reference to the original value is passed.
- [ ] A shallow copy is made.
- [ ] It throws an error.

### 3. Which keyword is used to define a reference type in C#?
- [ ] `struct`
- [ ] `enum`
- [x] `class`
- [ ] `readonly`

### 4. What is the output of the following code?
```csharp
int a = 10;
int b = a;
b = 20;
Console.WriteLine(a);
```
- [x] 10
- [ ] 20
- [ ] 0
- [ ] Compilation error

### 5. What is the output of the following code?
```csharp
class MyClass { public int Value; }

MyClass obj1 = new MyClass();
obj1.Value = 5;
MyClass obj2 = obj1;
obj2.Value = 10;
Console.WriteLine(obj1.Value);
```
- [ ] 5  
- [x] 10  
- [ ] 0  
- [ ] Compilation error

### 6. Which of the following is NOT a value type?
- [ ] `int`
- [x] `string`
- [ ] `bool`
- [ ] `double`

### 7. Strings in C# are:
- [ ] Mutable value types
- [ ] Mutable reference types
- [x] Immutable reference types
- [ ] Immutable value types

### 8. What is "boxing" in C#?
- [ ] Converting a reference type to a value type
- [x] Converting a value type to a reference type
- [ ] Copying the reference
- [ ] Creating a new class instance

### 9. Which of the following statements is true?
- [x] Value types are stored on the stack, reference types on the heap.
- [ ] Reference types are stored on the stack, value types on the heap.
- [ ] Both are stored on the heap.
- [ ] Both are stored on the stack.

### 10. Which of the following is a user-defined value type?
- [ ] `class`
- [ ] `delegate`
- [x] `struct`
- [ ] `array`
