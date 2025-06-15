## 📘 Section: Deployment and Tooling
### 🔹 Category: Continuous integration for Go projects
#### ✅ Answer 230: Continuous integration for Go projects

Continuous integration (CI) automates testing and code checks for every change in your Go project. Here is an example using GitHub Actions:

**Example: `.github/workflows/go.yml`**

```yaml
name: Go CI
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Set up Go
        uses: actions/setup-go@v5
        with:
          go-version: '1.21'
      - name: Install dependencies
        run: go mod tidy
      - name: Run tests
        run: go test ./...
      - name: Check formatting
        run: go fmt ./...
```

**Explanation:**
- This workflow runs on every push or pull request to the `main` branch.
- It checks out the code, sets up Go, installs dependencies, runs tests, and checks formatting.
- CI helps catch errors early and ensures code quality before merging changes.
