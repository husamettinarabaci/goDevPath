## 📘 Section: Go Modules and Dependency Management  
### 🔹 Category: Module Maintenance  
#### ✅ Answer 214: Using `go mod tidy`

The `go mod tidy` command ensures that your `go.mod` and `go.sum` files accurately reflect the dependencies used in your code. It removes unused dependencies and adds any that are required but missing.

**Step-by-step example:**

1. Suppose you add an import to your code but forget to run `go get`:
   ```go
   import "github.com/fatih/color"
   ```
   Running `go mod tidy` will add this dependency to `go.mod` and `go.sum`.
2. If you remove all uses of a package from your code, `go mod tidy` will remove it from `go.mod` and `go.sum`.
3. Example usage:
   ```bash
   go mod tidy
   ```

Keeping your module files tidy ensures reproducible builds, avoids unnecessary dependencies, and keeps your project clean and maintainable.
