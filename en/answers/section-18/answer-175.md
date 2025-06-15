## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Testing and Benchmarking  
#### ✅ Answer 175: Writing benchmarks

This example demonstrates how to write a benchmark in Go. The benchmark function uses the `b.N` loop to measure the performance of string concatenation.

`main.go`:
```go
package main

func Concat(a, b string) string {
    return a + b
}
```

`main_test.go`:
```go
package main
import "testing"

func BenchmarkConcat(b *testing.B) {
    for i := 0; i < b.N; i++ {
        _ = Concat("hello", "world")
    }
}
```

To run the benchmark, use:

```
go test -bench .
```

The output will show how many iterations were run and the average time per operation.
