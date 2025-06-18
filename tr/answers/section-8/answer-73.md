## 📘 Bölüm: Structlar  
### 🔹 Kategori: Birden fazla alan tipine sahip struct  
#### ✅ Cevap 73: Birden fazla alan tipine sahip struct

Go'da bir struct, farklı tipte alanlara sahip olabilir. Burada, string, float64 ve bool alanları olan `Product` struct'ı tanımlanıyor, bir örneği oluşturulup ekrana yazdırılıyor.

```go
package main
import "fmt"

type Product struct {
    name    string
    price   float64
    inStock bool
}

func main() {
    p := Product{"Laptop", 1299.99, true}
    fmt.Println(p)
}
```
