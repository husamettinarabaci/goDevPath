## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Testing and Benchmarking  
#### ✅ Answer 174: Using test coverage tools

This example shows how to measure test coverage in Go. The `go test -cover` command reports the percentage of code covered by tests.

`main.go`:
```go
package main

func Subtract(a, b int) int {
    return a - b
}
```

`main_test.go`:
```go
package main
import "testing"

func TestSubtract(t *testing.T) {
    result := Subtract(5, 3)
    expected := 2
    if result != expected {
        t.Errorf("Subtract(5, 3) = %d; want %d", result, expected)
    }
}
```

To measure test coverage, run:

```
go test -cover
```

This will output something like:

```
PASS
coverage: 100.0% of statements
```

The coverage percentage shows how much of your code is executed by your tests. Higher coverage means more of your code is tested.
