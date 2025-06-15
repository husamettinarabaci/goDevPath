## 📘 Section: Common Patterns and Idioms
### 🔹 Category: Singleton pattern in Go
#### ✅ Answer 233: Singleton pattern in Go

The singleton pattern ensures that only one instance of a type exists in a program. In Go, the idiomatic way is to use `sync.Once` for thread safety.

```go
package main
import (
    "fmt"
    "sync"
)

type singleton struct {
    value int
}

var (
    instance *singleton
    once     sync.Once
)

func GetInstance() *singleton {
    once.Do(func() {
        instance = &singleton{value: 42}
    })
    return instance
}

func main() {
    var wg sync.WaitGroup
    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func(id int) {
            defer wg.Done()
            s := GetInstance()
            fmt.Printf("Goroutine %d: %p %v\n", id, s, s.value)
        }(i)
    }
    wg.Wait()
}
```

This guarantees that only one instance is created, even with concurrent access.
