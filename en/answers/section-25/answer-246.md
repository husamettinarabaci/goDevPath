## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: Networking and Communication  
#### ✅ Answer 246: Building a chat application

This solution demonstrates a simple TCP-based chat application in Go. The server accepts multiple clients and broadcasts messages to all connected clients. Each client can send and receive messages in real time. The implementation uses the `net` package, goroutines, and channels.

**Server:**
```go
package main

import (
    "bufio"
    "fmt"
    "net"
    "os"
)

type client chan<- string

func broadcaster(clients map[client]bool, messages chan string, entering chan client, leaving chan client) {
    for {
        select {
        case msg := <-messages:
            for cli := range clients {
                cli <- msg
            }
        case cli := <-entering:
            clients[cli] = true
        case cli := <-leaving:
            delete(clients, cli)
            close(cli)
        }
    }
}

func handleConn(conn net.Conn, messages chan string, entering chan client, leaving chan client) {
    ch := make(chan string)
    go clientWriter(conn, ch)

    entering <- ch
    input := bufio.NewScanner(conn)
    for input.Scan() {
        messages <- input.Text()
    }
    leaving <- ch
    conn.Close()
}

func clientWriter(conn net.Conn, ch <-chan string) {
    for msg := range ch {
        fmt.Fprintln(conn, msg)
    }
}

func main() {
    listener, err := net.Listen("tcp", ":9001")
    if err != nil {
        fmt.Println("Error:", err)
        os.Exit(1)
    }
    defer listener.Close()
    messages := make(chan string)
    entering := make(chan client)
    leaving := make(chan client)
    clients := make(map[client]bool)

    go broadcaster(clients, messages, entering, leaving)
    fmt.Println("Chat server started on :9001")
    for {
        conn, err := listener.Accept()
        if err != nil {
            continue
        }
        go handleConn(conn, messages, entering, leaving)
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
    conn, err := net.Dial("tcp", "localhost:9001")
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    defer conn.Close()

    go func() {
        scanner := bufio.NewScanner(conn)
        for scanner.Scan() {
            fmt.Println(scanner.Text())
        }
    }()

    input := bufio.NewScanner(os.Stdin)
    for input.Scan() {
        fmt.Fprintln(conn, input.Text())
    }
}
```
