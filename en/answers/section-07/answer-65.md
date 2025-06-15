## 📘 Section: Pointers and Memory  
### 🔹 Category: Pointer Usage, new/make, Struct Pointers  
#### ✅ Answer 65: Pointer arithmetic (not allowed in Go)

In Go, pointer arithmetic (such as adding or subtracting integers to pointers) is not allowed, unlike in C or C++. This restriction improves memory safety and prevents bugs related to invalid memory access.

```go
package main
func main() {
    var x int
    p := &x
    // The following line will not compile:
    // p = p + 1
}
```

Attempting to perform pointer arithmetic in Go results in a compile-time error:

```
invalid operation: p + 1 (mismatched types *int and int)
```

Go enforces this rule to avoid unsafe memory manipulation and to keep programs safe and simple.
