## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Testing and Benchmarking  
#### ✅ Answer 171: Writing a basic test with `testing` package

This example shows how to write a simple function and a corresponding test using Go's `testing` package. The test checks if the addition function returns the correct result and reports an error if not.

`main.go`:
```go
package main

func Add(a, b int) int {
    return a + b
}
```

`main_test.go`:
```go
package main
import "testing"

func TestAdd(t *testing.T) {
    result := Add(2, 3)
    expected := 5
    if result != expected {
        t.Errorf("Add(2, 3) = %d; want %d", result, expected)
    }
}
```
