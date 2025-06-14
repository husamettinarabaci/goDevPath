## 📘 Bölüm: Başlangıç  
### 🔹 Kategori: main Fonksiyonu ve Yazdırma  
#### ✅ Cevap 6: `go mod init` ile basit bir Go projesi oluşturma

Bu örnek, modüller kullanarak basit bir Go projesinin nasıl oluşturulacağını gösterir. `go mod init` komutu yeni bir modül başlatır ve `main.go` dosyası temel bir Go programı içerir.

```go
// Terminalde bu komutu çalıştırarak modül başlatın:
// go mod init ornek.com/benimprojem

package main
import "fmt"

func main() {
    fmt.Println("Go modülleri!")
}
```
