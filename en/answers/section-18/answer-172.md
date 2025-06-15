## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Testing and Benchmarking  
#### ✅ Answer 172: Table-driven tests

This example demonstrates how to write a table-driven test in Go. The multiplication function is tested with multiple input cases using a slice of structs, and errors are reported for any mismatches.

`main.go`:
```go
package main

func Multiply(a, b int) int {
    return a * b
}
```

`main_test.go`:
```go
package main
import "testing"

func TestMultiply(t *testing.T) {
    tests := []struct {
        a, b   int
        result int
    }{
        {2, 3, 6},
        {0, 5, 0},
        {-1, 4, -4},
        {7, -2, -14},
    }
    for _, tt := range tests {
        got := Multiply(tt.a, tt.b)
        if got != tt.result {
            t.Errorf("Multiply(%d, %d) = %d; want %d", tt.a, tt.b, got, tt.result)
        }
    }
}
```
