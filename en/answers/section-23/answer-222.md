## 📘 Section: Deployment and Tooling  
### 🔹 Category: Building, cross-compiling, Docker, CI  
#### ✅ Answer 222: Cross-compiling Go programs

Go makes it easy to cross-compile programs for different platforms by setting the `GOOS` and `GOARCH` environment variables before running `go build`. For example, to build a Linux binary on macOS or Windows:

```bash
GOOS=linux GOARCH=amd64 go build -o myapp-linux main.go
```

This command creates a Linux 64-bit binary named `myapp-linux` from `main.go`. You can change `GOOS` and `GOARCH` to target other platforms (e.g., `windows`, `darwin`, `arm64`).
