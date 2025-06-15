## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: Networking and Communication  
#### ✅ Answer 245: Building a TCP server and client

This solution demonstrates a simple TCP server and client in Go. The server listens for connections, reads messages from clients, and echoes them back. The client connects to the server, sends a message, and prints the response. Both use the `net` package.

**Server:**
```go
package main

import (
    "bufio"
    "fmt"
    "net"
    "os"
)

func main() {
    ln, err := net.Listen("tcp", ":9000")
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    defer ln.Close()
    fmt.Println("Server listening on :9000")
    for {
        conn, err := ln.Accept()
        if err != nil {
            fmt.Println("Accept error:", err)
            continue
        }
        go handleConnection(conn)
    }
}

func handleConnection(conn net.Conn) {
    defer conn.Close()
    reader := bufio.NewReader(conn)
    for {
        msg, err := reader.ReadString('\n')
        if err != nil {
            return
        }
        conn.Write([]byte("Echo: " + msg))
    }
}
```

**Client:**
```go
package main

import (
    "bufio"
    "fmt"
    "net"
    "os"
)

func main() {
    conn, err := net.Dial("tcp", "localhost:9000")
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    defer conn.Close()

    fmt.Print("Enter message: ")
    input := bufio.NewReader(os.Stdin)
    msg, _ := input.ReadString('\n')
    conn.Write([]byte(msg))

    response, _ := bufio.NewReader(conn).ReadString('\n')
    fmt.Println("Server response:", response)
}
```
