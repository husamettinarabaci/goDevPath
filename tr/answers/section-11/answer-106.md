## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Metotlar ve Arayüzler  
#### ✅ Cevap 106: Bir arayüzü uygulama

Go'da bir arayüzü uygulamak için önce arayüz tipini tanımlayın, ardından bu arayüzdeki metodları karşılayan bir struct oluşturun. Bir tip, bir arayüzdeki tüm metodları uyguladığında o arayüzü karşılamış olur.

```go
package main
import "fmt"

// Arayüzü tanımla
type Greeter interface {
    Greet() string
}

// Arayüzü uygulayan struct
type Person struct {
    Name string
}

// Greet metodunu uygula
func (p Person) Greet() string {
    return "Merhaba, " + p.Name
}

func main() {
    var g Greeter = Person{Name: "Go Geliştiricisi"}
    fmt.Println(g.Greet())
}
```
