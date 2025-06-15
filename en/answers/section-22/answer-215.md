## 📘 Section: Go Modules and Dependency Management  
### 🔹 Category: Vendor Directory  
#### ✅ Answer 215: Using `go mod vendor`

The `go mod vendor` command copies all dependencies required by your project into a local `vendor` directory. This allows you to build your project without downloading dependencies from the internet, which is useful for reproducible builds, offline development, or compliance reasons.

**Step-by-step example:**

1. Add a dependency (e.g., `github.com/fatih/color`):
   ```bash
   go get github.com/fatih/color
   ```
2. Create the vendor directory:
   ```bash
   go mod vendor
   ```
   This copies all dependencies into the `vendor/` folder.
3. Build your project using vendored dependencies:
   ```bash
   go build -mod=vendor
   ```

Vendoring is useful when you want to ensure all dependencies are available locally, such as in CI/CD pipelines, air-gapped environments, or to comply with organizational policies.
