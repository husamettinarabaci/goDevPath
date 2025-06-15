## 📘 Section: Deployment and Tooling  
### 🔹 Category: Building, cross-compiling, Docker, CI  
#### ✅ Answer 228: Using `go run` and `go install`

`go run` compiles and runs Go programs directly from source files, while `go install` builds and installs the binary to your Go bin directory.

Example usage:

```bash
go run main.go
go install
```

- `go run main.go` compiles and runs `main.go` immediately.
- `go install` builds the binary and places it in your `$GOBIN` or `$GOPATH/bin` directory, making it available system-wide.

Use `go run` for quick testing and `go install` for installing reusable commands.
