## 📘 Bölüm: Mapler  
### 🔹 Kategori: Map Değerlerine Güvenli Erişim  
#### ✅ Cevap 93: Map değerlerine güvenli erişim

Go'da map değerlerine güvenli erişim için "virgül ok" idiomu kullanılır. Bu, anahtarın map'te olup olmadığını kontrol etmenizi sağlar. Örnek:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"elma": 5, "muz": 3}
    value, ok := m["elma"]
    if ok {
        fmt.Println("elma mevcut, değeri:", value)
    } else {
        fmt.Println("elma mevcut değil")
    }
    value, ok = m["portakal"]
    if ok {
        fmt.Println("portakal mevcut, değeri:", value)
    } else {
        fmt.Println("portakal mevcut değil")
    }
}
```

Bu programda anahtarın varlığı kontrol edilerek güvenli erişim sağlanmıştır.
