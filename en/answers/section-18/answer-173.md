## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Testing and Benchmarking  
#### ✅ Answer 173: Testing error conditions

This example demonstrates how to test both normal and error conditions in Go. The division function returns an error if the divisor is zero, and the test checks both successful and error cases.

`main.go`:
```go
package main
import "errors"

func Divide(a, b int) (int, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}
```

`main_test.go`:
```go
package main
import "testing"

func TestDivide(t *testing.T) {
    result, err := Divide(10, 2)
    if err != nil || result != 5 {
        t.Errorf("Divide(10, 2) = %d, %v; want 5, nil", result, err)
    }

    _, err = Divide(10, 0)
    if err == nil {
        t.Errorf("Divide(10, 0) did not return error; want error")
    }
}
```
