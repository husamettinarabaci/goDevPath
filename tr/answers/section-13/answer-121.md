## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: Paket oluşturma ve kullanma  
#### ✅ Cevap 121: Paket oluşturma ve kullanma

Go'da kodunuzu modüler ve tekrar kullanılabilir hale getirmek için paketler kullanabilirsiniz. Özel bir paket kullanmak için bir dizin oluşturup `.go` dosyası ekleyin, fonksiyonunuzu dışa aktarın ve `main` paketinizde içe aktarın.

Aşağıda bir örnek görebilirsiniz:

**selamla/selamla.go**
```go
package selamla

func Merhaba() string {
    return "Selamlar, selamla paketinden!"
}
```

**main.go**
```go
package main
import (
    "fmt"
    "selamla"
)

func main() {
    fmt.Println(selamla.Merhaba())
}
```

Bu örnekte, özel bir paket (`selamla`) oluşturulmuş, dışa açık bir fonksiyon tanımlanmış ve `main` paketinde kullanılmıştır. `selamla` dizininin `main.go` ile aynı seviyede veya modül kökünde olduğundan emin olun.
