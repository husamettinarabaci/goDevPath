## 📘 Section: Go Modules and Dependency Management  
### 🔹 Category: Upgrading and Downgrading Dependencies  
#### ✅ Answer 213: Upgrading and downgrading dependencies

Go modules make it easy to upgrade or downgrade dependencies using the `go get` command with a version suffix.

**Step-by-step example:**

1. Add a dependency (e.g., `github.com/fatih/color`):
   ```bash
   go get github.com/fatih/color
   ```
2. Upgrade to a newer version:
   ```bash
   go get github.com/fatih/color@v1.15.0
   ```
   This updates `go.mod` and `go.sum` to the specified version.
3. Downgrade to an older version:
   ```bash
   go get github.com/fatih/color@v1.10.0
   ```
   Again, `go.mod` and `go.sum` are updated.
4. Use the dependency in your code:
   ```go
   package main
   import "github.com/fatih/color"
   func main() {
       color.Green("This is green text!")
   }
   ```

After each `go get` command, check the `go.mod` and `go.sum` files to see the version changes. This ensures your project uses the exact dependency versions you specify.
