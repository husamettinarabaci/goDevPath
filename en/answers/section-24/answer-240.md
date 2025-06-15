## 📘 Section: Common Patterns and Idioms  
### 🔹 Category: Writing idiomatic Go code  
#### ✅ Answer 240: Writing idiomatic Go code

Idiomatic Go code follows conventions that make programs readable, maintainable, and robust. Key idioms include short variable names, explicit error handling, use of `defer` for cleanup, and composition over inheritance.

```go
package main

import (
    "fmt"
    "os"
)

type Logger struct {
    prefix string
}

func (l Logger) Log(msg string) {
    fmt.Println(l.prefix, msg)
}

func main() {
    file, err := os.Open("data.txt")
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    defer file.Close()

    logger := Logger{prefix: "INFO:"}
    logger.Log("File opened successfully")

    // Idiomatic loop
    for i := 0; i < 3; i++ {
        fmt.Println("Iteration", i)
    }

    // Idiomatic conditional
    if file != nil {
        fmt.Println("File is ready for use.")
    }
}
```

Following Go idioms leads to code that is easier to read, less error-prone, and more maintainable.
