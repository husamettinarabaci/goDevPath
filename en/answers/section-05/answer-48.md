## 📘 Section: Functions I  
### 🔹 Category: Function Definition and Usage  
#### ✅ Answer 48: Function with anonymous parameters

This solution defines a function `printFirst` that takes two integer parameters but only uses the first. The second parameter is anonymous (underscore). The function is called from `main` and prints the first parameter.

```go
package main
import "fmt"

func printFirst(a int, _ int) {
    fmt.Println("First parameter:", a)
}

func main() {
    printFirst(10, 99)
}
```
