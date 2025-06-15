## 📘 Section: Networking and HTTP  
### 🔹 Category: Networking and HTTP  
#### ✅ Answer 199: Using WebSockets in Go

This program demonstrates how to implement a simple WebSocket echo server in Go using the `github.com/gorilla/websocket` package. The server listens on port 8080 and echoes back any message received from the client at the `/ws` endpoint.

```go
package main
import (
    "fmt"
    "net/http"
    "github.com/gorilla/websocket"
)

var upgrader = websocket.Upgrader{}

func wsHandler(w http.ResponseWriter, r *http.Request) {
    conn, err := upgrader.Upgrade(w, r, nil)
    if err != nil {
        fmt.Println("Upgrade error:", err)
        return
    }
    defer conn.Close()
    for {
        mt, message, err := conn.ReadMessage()
        if err != nil {
            fmt.Println("Read error:", err)
            break
        }
        fmt.Printf("Received: %s\n", message)
        if err := conn.WriteMessage(mt, message); err != nil {
            fmt.Println("Write error:", err)
            break
        }
    }
}

func main() {
    http.HandleFunc("/ws", wsHandler)
    fmt.Println("WebSocket server started at ws://localhost:8080/ws")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Server error:", err)
    }
}
```

> Note: You need to run `go get github.com/gorilla/websocket` to install the required package.
