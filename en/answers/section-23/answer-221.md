## 📘 Section: Deployment and Tooling
### 🔹 Category: Building and Binaries
#### ✅ Answer 221: Building Go binaries

To build a Go program into a binary executable, use the `go build` command. By default, this creates a binary in the current directory with the same name as the containing folder.

- To specify the output binary name, use the `-o` flag:

```bash
go build -o myapp main.go
```

- The binary is created in the current directory unless you specify a different path.
- Example:

```bash
go build
```

This will build the program in the current directory and produce an executable file.
