## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: File System Utilities  
#### ✅ Answer 244: Building a file watcher utility

This solution demonstrates a file watcher utility in Go using the `fsnotify` package. The program monitors a directory for file creation, modification, and deletion events, and prints a message for each event. The watcher runs until the program is manually stopped.

```go
package main

import (
    "fmt"
    "log"
    "os"
    "github.com/fsnotify/fsnotify"
)

func main() {
    if len(os.Args) < 2 {
        fmt.Println("Usage: go run main.go <directory>")
        return
    }
    dir := os.Args[1]
    watcher, err := fsnotify.NewWatcher()
    if err != nil {
        log.Fatal(err)
    }
    defer watcher.Close()

    err = watcher.Add(dir)
    if err != nil {
        log.Fatal(err)
    }

    fmt.Printf("Watching directory: %s\n", dir)
    for {
        select {
        case event, ok := <-watcher.Events:
            if !ok {
                return
            }
            fmt.Printf("Event: %s %s\n", event.Op, event.Name)
        case err, ok := <-watcher.Errors:
            if !ok {
                return
            }
            fmt.Println("Error:", err)
        }
    }
}
```

> Note: Install the `fsnotify` package with `go get github.com/fsnotify/fsnotify`.
