## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: Struct'lara pointer ile erişim  
#### ✅ Cevap 69: Struct'lara pointer ile erişim

Struct'lara pointer ile erişmek, struct'ın alanlarını adresi üzerinden değiştirmeye olanak tanır. Burada, `Person` struct'ı tanımlanıyor, pointer ile alanlar güncelleniyor ve değişiklikler ekrana yazdırılıyor.

```go
package main
import "fmt"

type Person struct {
    name string
    age  int
}

func main() {
    p := Person{"Alice", 30}
    fmt.Println(p) // değişiklikten önce

    ptr := &p
    ptr.name = "Bob"
    ptr.age = 40

    fmt.Println(p) // değişiklikten sonra
}
```
