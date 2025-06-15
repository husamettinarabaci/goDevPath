## 📘 Section: Methods and Interfaces I  
### 🔹 Category: Methods  
#### ✅ Answer 104: Method with multiple receivers (not allowed in Go)

Go does not allow methods with multiple receivers. Each method can have only one receiver, which is the type the method is associated with. Attempting to define a method with multiple receivers results in a compile-time error. Here is an invalid example and the correct approach:

**Invalid (not allowed):**
```go
// This will not compile in Go
func (a A, b B) DoSomething() {}
```

**Correct way:**
```go
type A struct{}
type B struct{}

func (a A) DoSomethingWithB(b B) {
    // Use both a and b inside the method
}
```

You can only have one receiver, but you can pass other types as parameters.
