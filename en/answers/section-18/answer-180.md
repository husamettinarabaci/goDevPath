## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Best practices for testing  
#### ✅ Answer 180: Best practices for testing

Best practices for Go testing include:

- **Test isolation:** Each test should be independent and not rely on shared state.
- **Clear naming:** Test functions should be descriptive (e.g., `TestAddNumbers`).
- **Reproducibility:** Tests should produce the same result every run.
- **Use of `t.Helper()`:** Mark helper functions to improve error reporting.
- **Table-driven tests:** Use slices of test cases for similar logic.
- **Check errors:** Always check and handle errors in tests.
- **Keep tests close to code:** Place tests in the same package as the code.

Example of a good test:

```go
func TestAdd(t *testing.T) {
    got := Add(2, 3)
    want := 5
    if got != want {
        t.Errorf("Add(2, 3) = %d; want %d", got, want)
    }
}
```

Example of a bad test:

```go
func TestAdd(t *testing.T) {
    if Add(2, 3) != 5 {
        // no error message, hard to debug
    }
}
```

Good tests are clear, isolated, and provide useful feedback when they fail.
