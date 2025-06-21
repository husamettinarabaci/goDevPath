## 📘 Section: Structs and Methods  
### 🔹 Category: Struct Embedding  
#### ✅ Answer 254: Struct embedding and inheritance-like behavior

Struct embedding in Go allows one struct to include another, providing inheritance-like behavior. Here, `Dog` embeds `Animal` and adds a `Breed` field.

```go
package main
import "fmt"

type Animal struct {
    Name string
}

type Dog struct {
    Animal
    Breed string
}

func main() {
    d := Dog{Animal: Animal{Name: "Buddy"}, Breed: "Golden Retriever"}
    fmt.Println("Name:", d.Name)
    fmt.Println("Breed:", d.Breed)
}
```
