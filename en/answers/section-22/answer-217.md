## 📘 Section: Go Modules and Dependency Management
### 🔹 Category: go.mod and Dependency Management
#### ✅ Answer 217: Using private modules

Private modules are Go modules stored in repositories that are not publicly accessible. To use them:

- Set the `GOPRIVATE` environment variable to match the module path (e.g., `export GOPRIVATE=github.com/yourorg/*`).
- Configure authentication (e.g., SSH keys or personal access tokens) for your Git provider.
- Use the private module in your `go.mod` as you would with any public module:

```
require github.com/yourorg/privatemod v1.2.3
```

Go will use your credentials to fetch the module. Make sure your environment is set up to allow access to the private repository.