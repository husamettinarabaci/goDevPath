## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Interface Embedding  
#### ✅ Answer 111: Embedding interfaces

In Go, you can embed interfaces within other interfaces to create more complex abstractions. A struct that implements all the methods of the embedded interfaces satisfies the new interface. Here is an example:

```go
package main
import "fmt"

type Reader interface {
    Read() string
}

type Writer interface {
    Write(s string)
}

type ReadWriter interface {
    Reader
    Writer
}

type File struct {
    content string
}

func (f *File) Read() string {
    return f.content
}

func (f *File) Write(s string) {
    f.content = s
}

func useReadWriter(rw ReadWriter) {
    rw.Write("Hello, Go!")
    fmt.Println(rw.Read())
}

func main() {
    f := &File{}
    useReadWriter(f)
}
```
