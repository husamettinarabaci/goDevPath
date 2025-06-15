## 📘 Section: Deployment and Tooling  
### 🔹 Category: Using Docker with Go  
#### ✅ Answer 229: Using Docker with Go

To containerize a Go application, use a multi-stage Docker build for a small, production-ready image. Here’s how:

1. **main.go**
```go
package main
import "fmt"
func main() {
    fmt.Println("Hello from Dockerized Go!")
}
```

2. **Dockerfile**
```Dockerfile
# Build stage
FROM golang:1.21-alpine AS builder
WORKDIR /app
COPY main.go ./
RUN go build -o app main.go

# Final image
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/app .
CMD ["./app"]
```

3. **Build and run the container:**
```sh
docker build -t go-docker-demo .
docker run --rm go-docker-demo
```

This approach keeps the final image small and only includes the compiled binary.
