## 📘 Section: Common Patterns and Idioms  
### 🔹 Category: Logging best practices  
#### ✅ Answer 239: Logging best practices

Proper logging is essential for debugging, monitoring, and maintaining Go applications. The standard `log` package provides basic logging, and third-party libraries offer advanced features like levels and structured output.

```go
package main

import (
    "log"
    "os"
)

func main() {
    // Log to a file
    file, err := os.OpenFile("app.log", os.O_CREATE|os.O_WRONLY|os.O_APPEND, 0666)
    if err != nil {
        log.Fatalf("Failed to open log file: %v", err)
    }
    log.SetOutput(file)
    log.SetFlags(log.Ldate | log.Ltime | log.Lshortfile)

    log.Println("INFO: Application started")
    log.Println("WARNING: This is a warning message")
    log.Println("ERROR: This is an error message")
}
```

For advanced logging (levels, structured logs), consider using a package like `logrus` or `zap`:

```go
// Example with logrus
import log "github.com/sirupsen/logrus"

log.WithFields(log.Fields{
    "user": "alice",
    "operation": "login",
}).Info("User login event")
```

Proper logging helps track application flow, errors, and important events, making troubleshooting and monitoring easier.
