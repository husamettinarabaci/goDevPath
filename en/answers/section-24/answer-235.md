## 📘 Section: Common Patterns and Idioms
### 🔹 Category: Dependency injection basics
#### ✅ Answer 235: Dependency injection basics

Dependency injection is a technique where dependencies are provided to a component rather than hardcoded. In Go, this is often done via struct fields or constructor functions, making code more testable and flexible.

```go
package main
import "fmt"

type Logger interface {
    Log(msg string)
}

type ConsoleLogger struct{}
func (c ConsoleLogger) Log(msg string) { fmt.Println(msg) }

type Service struct {
    logger Logger
}

func NewService(l Logger) *Service {
    return &Service{logger: l}
}

func (s *Service) DoSomething() {
    s.logger.Log("Doing something!")
}

func main() {
    logger := ConsoleLogger{}
    service := NewService(logger)
    service.DoSomething()
}
```

This approach allows you to inject a mock logger in tests, improving testability.
