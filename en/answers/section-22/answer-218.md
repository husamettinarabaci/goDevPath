## 📘 Section: Go Modules and Dependency Management
### 🔹 Category: go.mod and Dependency Management
#### ✅ Answer 218: Semantic versioning in Go modules

Semantic versioning (semver) is a versioning scheme that uses a three-part number: `MAJOR.MINOR.PATCH` (e.g., `v1.2.3`).

- **MAJOR** version changes when you make incompatible API changes.
- **MINOR** version changes when you add functionality in a backward-compatible manner.
- **PATCH** version changes when you make backward-compatible bug fixes.

Go modules use semantic versioning to manage dependencies and ensure compatibility. Versions are always prefixed with `v`, such as `v1.0.0`, `v2.3.1`, or `v0.9.5`.

Following semver is important because it helps users of your module know when breaking changes are introduced, and it allows Go's module system to resolve dependencies safely.

**Examples of valid Go module versions:**
- `v1.0.0`
- `v2.1.3`
- `v0.9.5`

You specify versions in `go.mod` or when running `go get`, for example:

```
go get example.com/mod@v1.2.3
```

This ensures the correct version is used in your project.