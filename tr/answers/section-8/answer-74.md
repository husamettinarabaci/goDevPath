## 📘 Bölüm: Structlar  
### 🔹 Kategori: Struct Gömme (Composition)  
#### ✅ Cevap 74: Struct gömme (composition)

Struct gömme (composition), daha basit tiplerden karmaşık tipler oluşturmanıza olanak tanır. Burada `Employee`, `Person` struct'ını gömüyor ve böylece onun alanlarını ve metodlarını miras alıyor. Gömülü alanlara dış struct üzerinden doğrudan erişebilirsiniz.

```go
package main
import "fmt"

type Person struct {
    name string
    age  int
}

type Employee struct {
    Person
    position string
}

func main() {
    emp := Employee{
        Person: Person{name: "Alice", age: 30},
        position: "Developer",
    }
    fmt.Println("İsim:", emp.name)
    fmt.Println("Yaş:", emp.age)
    fmt.Println("Pozisyon:", emp.position)
}
```
