## 📘 Bölüm: Değişkenler, Sabitler ve Tipler  
### 🔹 Kategori: Tip Çıkarımı  
#### ✅ Cevap 15: Değişken tanımlamada tip çıkarımı

Go'da değişken tanımlarken tip belirtmeden değer atayabilirsiniz. Go, tipini otomatik olarak çıkarır. Aşağıda bir örnek yer almaktadır:

```go
package main
import "fmt"
func main() {
    isim := "Zeynep"    // string olarak çıkarılır
    yas := 30            // int olarak çıkarılır
    oran := 2.71         // float64 olarak çıkarılır
    fmt.Printf("isim: %v (%T)\n", isim, isim)
    fmt.Printf("yas: %v (%T)\n", yas, yas)
    fmt.Printf("oran: %v (%T)\n", oran, oran)
}
```

Bu program, kısa değişken tanımlama (`:=`) ile tip çıkarımını göstermektedir.
