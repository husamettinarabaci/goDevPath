## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Using `go test` Flags  
#### ✅ Answer 176: Using `go test` flags

You can use various `go test` flags to control test execution and output. The `-v` flag enables verbose output, `-run` allows running specific tests, and `-cover` shows code coverage.

Example test file:

```go
def add(a, b int) int {
    return a + b
}

import "testing"

func TestAdd(t *testing.T) {
    result := add(2, 3)
    if result != 5 {
        t.Errorf("Expected 5, got %d", result)
    }
}
```

Example commands:

- Run all tests verbosely:
  ```sh
  go test -v
  ```
- Run only tests matching `Add`:
  ```sh
  go test -run=Add
  ```
- Run tests with coverage:
  ```sh
  go test -cover
  ```

These flags help you control which tests run, see detailed output, and measure code coverage.
