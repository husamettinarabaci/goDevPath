## 📘 Section: Variables, Constants, and Types  
### 🔹 Category: String Variables  
#### ✅ Answer 16: Creating and using string variables

In Go, you can declare string variables, assign values, and concatenate strings. Here is an example:

```go
package main
import "fmt"
func main() {
    var greeting string = "Hello"
    fmt.Println(greeting)
    name := "Go Developer"
    message := greeting + ", " + name + "!"
    fmt.Println(message)
}
```

This program demonstrates declaring, using, and concatenating string variables.
