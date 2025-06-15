## 📘 Section: Advanced Go Features  
### 🔹 Category: Build Tags  
#### ✅ Answer 204: Using build tags

Build tags in Go allow you to include or exclude files from a build based on conditions like OS or architecture. Here is an example for Linux and Windows:

`main_linux.go`:
```go
//go:build linux
// +build linux

package main

func PrintOS() {
    println("Running on Linux")
}
```

`main_windows.go`:
```go
//go:build windows
// +build windows

package main

func PrintOS() {
    println("Running on Windows")
}
```

`main.go`:
```go
package main

func main() {
    PrintOS()
}
```

When you build on Linux, `PrintOS` from `main_linux.go` is used; on Windows, `main_windows.go` is used. Build tags are placed at the top of the file and control file inclusion during compilation.
