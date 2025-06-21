## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Struct Gömme  
#### ✅ Cevap 254: Struct gömme ve kalıtım benzeri davranış

Go'da struct gömme, bir struct'ın başka bir struct'ı içermesini sağlar ve kalıtım benzeri bir davranış sunar. Burada `Dog`, `Animal`'ı gömer ve ek olarak `Breed` alanı ekler.

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
    fmt.Println("İsim:", d.Name)
    fmt.Println("Irk:", d.Breed)
}
```
