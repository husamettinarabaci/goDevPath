## 📘 Section: Packages and Imports  
### 🔹 Category: Documentation and GoDoc  
#### ✅ Answer 129: Documentation with GoDoc

GoDoc generates documentation from specially formatted comments in your Go code. Comments immediately preceding a package, function, type, or field that begin with the name of the item are included in the generated documentation. Exported identifiers (starting with a capital letter) are documented.

```go
// Package mathutil provides utility mathematical functions.
package mathutil

// Add returns the sum of two integers.
func Add(a, b int) int {
    return a + b
}
```

To view the documentation, run `go doc mathutil` or use an online GoDoc viewer. This helps others understand your code and its usage.
