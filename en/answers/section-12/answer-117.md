## 📘 Section: Methods and Interfaces II  
### 🔹 Category: Interface composition  
#### ✅ Answer 117: Interface composition

In Go, interface composition allows you to build more complex interfaces by embedding multiple interfaces into a new one. A struct that implements all embedded methods satisfies the composed interface.

Below is an example:

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

func main() {
    var rw ReadWriter = &File{}
    rw.Write("Hello, Go!")
    fmt.Println(rw.Read())
}
```

Here, `ReadWriter` composes `Reader` and `Writer`. The `File` struct implements both, so it satisfies `ReadWriter`.
