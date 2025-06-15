## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: Building a CLI tool in Go  
#### ✅ Answer 241: Building a CLI tool in Go

A simple CLI tool in Go can be built using the `flag` package or by directly accessing `os.Args`. Here is an example that echoes a message provided as a command-line argument:

```go
package main

import (
    "flag"
    "fmt"
    "os"
)

func main() {
    msg := flag.String("msg", "", "Message to echo")
    flag.Parse()

    if *msg == "" {
        fmt.Println("Usage: cli-tool -msg <your message>")
        os.Exit(1)
    }

    fmt.Println("Echo:", *msg)
}
```

This program uses the `flag` package to parse a `-msg` argument. If no message is provided, it prints a usage message. This is a basic pattern for building CLI tools in Go.
