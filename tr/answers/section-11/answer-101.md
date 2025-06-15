## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Metotlar  
#### ✅ Cevap 101: Structlara metot tanımlama

Go'da struct tiplerine metot tanımlayabilirsiniz. Metot, alıcı (receiver) parametresi olan bir fonksiyondur. Örnek:

```go
package main
import "fmt"

type Person struct {
    Name string
}

func (p Person) Selamla() {
    fmt.Println("Merhaba, benim adım", p.Name)
}

func main() {
    kisi := Person{Name: "Ayşe"}
    kisi.Selamla()
}
```
