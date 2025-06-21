## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Structlar  
#### ✅ Cevap 251: Struct tanımlama ve alanları

Go'da struct, birden fazla alanı bir araya getiren bileşik bir tiptir. Burada `Person` adında, `Name` ve `Age` alanlarına sahip bir struct tanımlanır, bir örneği oluşturulur ve değerleri yazdırılır.

```go
package main
import "fmt"

type Person struct {
    Name string
    Age  int
}

func main() {
    p := Person{Name: "Alice", Age: 30}
    fmt.Println("Name:", p.Name)
    fmt.Println("Age:", p.Age)
}
```
