## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: Özel Hata Tipleri Oluşturma  
#### ✅ Cevap 133: Özel hata tipleri oluşturma

Go'da özel hata tipleri oluşturmak için bir struct tanımlayıp `Error()` metodunu uygularsınız. Bu, hatalara ekstra bilgi eklemenizi sağlar.

```go
package main

import "fmt"

type NegatifHata struct {
    Deger int
}

func (e *NegatifHata) Error() string {
    return fmt.Sprintf("negatif değer: %d", e.Deger)
}

func pozitifKontrol(n int) error {
    if n < 0 {
        return &NegatifHata{Deger: n}
    }
    return nil
}

func main() {
    if err := pozitifKontrol(-5); err != nil {
        fmt.Println("Hata:", err)
    } else {
        fmt.Println("Değer geçerli.")
    }
}
```

Bu desen, hatalara ayrıntılı bilgi eklemek için kullanışlıdır.
