## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Organizing test files  
#### ✅ Answer 179: Organizing test files

In Go, test files should be named with the `_test.go` suffix and placed in the same package as the code they test. Test functions should start with `Test` and take a `*testing.T` parameter. Organizing tests by package and using subdirectories for larger projects improves clarity.

Example directory structure:

```
myproject/
├── main.go
├── main_test.go
├── utils/
│   ├── utils.go
│   └── utils_test.go
└── models/
    ├── user.go
    └── user_test.go
```

Example test function:

```go
// main_test.go
package main
import "testing"

func TestMainLogic(t *testing.T) {
    // test code here
}
```

This structure keeps tests close to the code, making them easy to find and maintain.
