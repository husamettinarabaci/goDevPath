## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: panic ve recover ile Hata Yönetimi  
#### ✅ Cevap 136: `panic` ve `recover` ile hata yönetimi

`panic` ve `recover`, Go'da beklenmeyen hataları yönetmek için kullanılır. `panic` normal akışı durdurur, `recover` ise bir `defer` fonksiyonu içinde panici yakalayabilir.

```go
package main

import "fmt"

func panikOlabilir(n int) {
    if n < 0 {
        panic("negatif değer kabul edilmez")
    }
    fmt.Println("Değer:", n)
}

func guvenliCagir(n int) {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Panic'ten kurtarıldı:", r)
        }
    }()
    panikOlabilir(n)
    fmt.Println("Fonksiyon normal tamamlandı.")
}

func main() {
    guvenliCagir(5)
    guvenliCagir(-2)
}
```

Bu örnek, Go'da hata yönetimi için `panic` ve `recover` kullanımını gösterir.
