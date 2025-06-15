## 📘 Section: Common Patterns and Idioms
### 🔹 Category: Functional options pattern
#### ✅ Answer 232: Functional options pattern

The functional options pattern allows flexible and readable configuration of structs or functions by passing option functions as arguments. This avoids long parameter lists and makes code more maintainable.

```go
package main
import "fmt"

type Server struct {
    Host string
    Port int
}

type Option func(*Server)

func WithHost(host string) Option {
    return func(s *Server) {
        s.Host = host
    }
}

func WithPort(port int) Option {
    return func(s *Server) {
        s.Port = port
    }
}

func NewServer(opts ...Option) *Server {
    s := &Server{Host: "localhost", Port: 8080}
    for _, opt := range opts {
        opt(s)
    }
    return s
}

func main() {
    srv := NewServer(WithHost("example.com"), WithPort(9090))
    fmt.Printf("Server: %+v\n", srv)
}
```

This pattern makes it easy to add new options without changing the constructor signature.
