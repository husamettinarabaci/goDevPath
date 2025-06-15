## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: `init` ile Paket Başlatma  
#### ✅ Cevap 126: `init` ile paket başlatma

Go'da `init` fonksiyonu, program başlatıldığında otomatik olarak `main` fonksiyonundan önce çalışır ve genellikle başlatma işlemleri için kullanılır. Örnek:

```go
package main

import "fmt"

func init() {
    fmt.Println("Paket başlatılıyor...")
}

func main() {
    fmt.Println("main fonksiyonu çalışıyor")
}
```

Bu programda, `init` fonksiyonundan gelen mesaj önce, `main` fonksiyonundan gelen mesaj ise sonra ekrana yazdırılır. Bu, çalıştırma sırasını gösterir.
