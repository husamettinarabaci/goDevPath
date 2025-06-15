## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Testing concurrent code  
#### ✅ Answer 178: Testing concurrent code

Testing concurrent code in Go requires careful synchronization to avoid race conditions and ensure correctness. The `sync.WaitGroup` is commonly used to wait for goroutines to finish, and the `-race` flag can help detect race conditions.

Example:

```go
package main
import (
    "sync"
    "testing"
)

func sumConcurrently(nums []int) int {
    var sum int
    var mu sync.Mutex
    var wg sync.WaitGroup
    for _, n := range nums {
        wg.Add(1)
        go func(val int) {
            defer wg.Done()
            mu.Lock()
            sum += val
            mu.Unlock()
        }(n)
    }
    wg.Wait()
    return sum
}

func TestSumConcurrently(t *testing.T) {
    nums := []int{1, 2, 3, 4, 5}
    result := sumConcurrently(nums)
    if result != 15 {
        t.Errorf("expected 15, got %d", result)
    }
}
```

Run the test with `go test -race` to check for race conditions.
