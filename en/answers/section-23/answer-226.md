## 📘 Section: Deployment and Tooling  
### 🔹 Category: Building, cross-compiling, Docker, CI  
#### ✅ Answer 226: Using `go fmt` and `goimports`

`go fmt` automatically formats Go source files according to standard style guidelines. `goimports` formats code and also manages import statements (adding/removing as needed).

Example usage:

```bash
go fmt ./...
goimports -w .
```

- `go fmt ./...` formats all Go files in the current module.
- `goimports -w .` formats and updates imports in all Go files recursively.

`goimports` is especially useful for keeping imports clean and up to date.
