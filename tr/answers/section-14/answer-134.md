## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: errors.New ve fmt.Errorf Kullanımı  
#### ✅ Cevap 134: `errors.New` ve `fmt.Errorf` kullanımı

Go'da `errors.New` ile basit hata, `fmt.Errorf` ile ise biçimlendirilmiş hata mesajları oluşturabilirsiniz.

```go
package main

import (
    "errors"
    "fmt"
)

func yasKontrol(yas int) error {
    if yas < 0 {
        return errors.New("yaş negatif olamaz")
    }
    if yas > 120 {
        return fmt.Errorf("yaş %d gerçekçi değil", yas)
    }
    return nil
}

func main() {
    if err := yasKontrol(-1); err != nil {
        fmt.Println("Hata:", err)
    }
    if err := yasKontrol(150); err != nil {
        fmt.Println("Hata:", err)
    }
    if err := yasKontrol(30); err != nil {
        fmt.Println("Hata:", err)
    } else {
        fmt.Println("Yaş geçerli.")
    }
}
```

Bu örnek, farklı durumlar için iki hata oluşturma yönteminin nasıl kullanılacağını gösterir.
