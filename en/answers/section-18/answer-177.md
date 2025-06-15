## 📘 Section: Testing and Benchmarking  
### 🔹 Category: Mocking in tests  
#### ✅ Answer 177: Mocking in tests

Mocking allows you to test code that depends on external resources by replacing them with controlled implementations. In Go, this is typically done by defining an interface and providing a mock implementation for testing.

Example:

```go
package main
import "testing"

// Dependency interface
type Greeter interface {
    Greet(name string) string
}

// Real implementation
type RealGreeter struct{}
func (g RealGreeter) Greet(name string) string {
    return "Hello, " + name
}

// Mock implementation for testing
type MockGreeter struct{}
func (g MockGreeter) Greet(name string) string {
    return "Hi, mock " + name
}

func GreetUser(g Greeter, name string) string {
    return g.Greet(name)
}

func TestGreetUser(t *testing.T) {
    mock := MockGreeter{}
    result := GreetUser(mock, "Go")
    if result != "Hi, mock Go" {
        t.Errorf("unexpected result: %s", result)
    }
}
```

This test uses a mock to verify the behavior of `GreetUser` without relying on the real implementation.
