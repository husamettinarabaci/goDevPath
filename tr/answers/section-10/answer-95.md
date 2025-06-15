## 📘 Bölüm: Mapler  
### 🔹 Kategori: Anahtar Varlığını Kontrol Etme  
#### ✅ Cevap 95: Anahtar varlığını kontrol etme

Go'da bir map'te anahtarın var olup olmadığını "virgül ok" idiomu ile kontrol edebilirsiniz. Örnek:

```go
package main
import "fmt"

func main() {
    m := map[string]int{"elma": 5, "muz": 3}
    if _, ok := m["elma"]; ok {
        fmt.Println("'elma' anahtarı map'te mevcut.")
    } else {
        fmt.Println("'elma' anahtarı map'te yok.")
    }
    if _, ok := m["portakal"]; ok {
        fmt.Println("'portakal' anahtarı map'te mevcut.")
    } else {
        fmt.Println("'portakal' anahtarı map'te yok.")
    }
}
```

Bu programda anahtarların varlığı kontrol edilip sonuçlar yazdırılmıştır.
