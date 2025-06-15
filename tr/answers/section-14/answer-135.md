## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: Hataları Sarmalama (Wrapping)  
#### ✅ Cevap 135: Hataları sarmalama (wrapping)

Go 1.13+ ile `%w` kullanarak `fmt.Errorf` ile hata sarmalama yapılabilir. `errors.Is` ve `errors.Unwrap` ile sarılmış hatalar incelenebilir.

```go
package main

import (
    "errors"
    "fmt"
)

var ErrBulunamadi = errors.New("bulunamadı")

func elemanBul(id int) error {
    if id != 1 {
        return ErrBulunamadi
    }
    return nil
}

func elemanGetir(id int) error {
    if err := elemanBul(id); err != nil {
        return fmt.Errorf("elemanGetir başarısız: %w", err)
    }
    return nil
}

func main() {
    err := elemanGetir(2)
    if err != nil {
        fmt.Println("Hata:", err)
        if errors.Is(err, ErrBulunamadi) {
            fmt.Println("Orijinal hata ErrBulunamadi")
        }
    }
}
```

Bu örnek, Go'da hata sarmalama ve incelemenin nasıl yapılacağını gösterir.
