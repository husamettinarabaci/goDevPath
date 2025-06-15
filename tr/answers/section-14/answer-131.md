## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: Fonksiyonlardan Hata Döndürme  
#### ✅ Cevap 131: Fonksiyonlardan hata döndürme

Go'da fonksiyonlardan genellikle son dönüş değeri olarak hata (`error`) döndürülür. Dahili `error` tipini ve `errors.New` fonksiyonunu kullanarak hata oluşturabilirsiniz.

```go
package main

import (
    "errors"
    "fmt"
)

func pozitifKontrol(n int) error {
    if n < 0 {
        return errors.New("değer negatif olamaz")
    }
    return nil
}

func main() {
    if err := pozitifKontrol(5); err != nil {
        fmt.Println("Hata:", err)
    } else {
        fmt.Println("Değer geçerli.")
    }

    if err := pozitifKontrol(-2); err != nil {
        fmt.Println("Hata:", err)
    } else {
        fmt.Println("Değer geçerli.")
    }
}
```

Bu desen, Go programlarında hataların düzgün şekilde ele alınmasını sağlar.
