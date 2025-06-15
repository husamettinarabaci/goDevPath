## 📘 Section: Advanced Go Features  
### 🔹 Category: Custom Collection Types  
#### ✅ Answer 207: Writing custom collection types

You can define your own collection types in Go using structs and methods. Here is an example of a simple stack:

```go
package main
import "fmt"

type Stack struct {
    items []int
}

func (s *Stack) Push(item int) {
    s.items = append(s.items, item)
}

func (s *Stack) Pop() int {
    if len(s.items) == 0 {
        panic("stack is empty")
    }
    item := s.items[len(s.items)-1]
    s.items = s.items[:len(s.items)-1]
    return item
}

func (s *Stack) Peek() int {
    if len(s.items) == 0 {
        panic("stack is empty")
    }
    return s.items[len(s.items)-1]
}

func main() {
    var s Stack
    s.Push(10)
    s.Push(20)
    fmt.Println(s.Peek()) // 20
    fmt.Println(s.Pop())  // 20
    fmt.Println(s.Pop())  // 10
}
```
