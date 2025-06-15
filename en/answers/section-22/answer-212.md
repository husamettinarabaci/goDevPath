## 📘 Section: Go Modules and Dependency Management  
### 🔹 Category: Adding Dependencies  
#### ✅ Answer 212: Adding dependencies with `go get`

To add external dependencies in a Go project, use the `go get` command. This downloads the package, updates your `go.mod` and `go.sum` files, and makes the package available for import.

**Step-by-step example:**

1. Initialize a Go module (if not already done):
   ```bash
   go mod init example.com/myproject
   ```
2. Add a dependency (e.g., `github.com/fatih/color`):
   ```bash
   go get github.com/fatih/color
   ```
   This updates `go.mod` and creates/updates `go.sum`.
3. Use the package in your code:
   ```go
   package main
   import "github.com/fatih/color"
   func main() {
       color.Red("This is red text!")
   }
   ```
4. Run your program:
   ```bash
   go run main.go
   ```

After running `go get`, your `go.mod` will include a line for the new dependency, and `go.sum` will record checksums for reproducible builds.
