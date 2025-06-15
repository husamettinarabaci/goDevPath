## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: error Tipini Kullanma  
#### ✅ Cevap 132: `error` tipini kullanma

Go'da yerleşik `error` tipi hata durumlarını temsil etmek için kullanılır. Bir fonksiyondan hata döndürebilir ve çağıran tarafta kontrol edebilirsiniz.

```go
package main

import (
    "errors"
    "fmt"
)

func bosOlmayanKontrol(s string) error {
    if s == "" {
        return errors.New("string boş olamaz")
    }
    return nil
}

func main() {
    if err := bosOlmayanKontrol(""); err != nil {
        fmt.Println("Hata:", err)
    } else {
        fmt.Println("String geçerli.")
    }

    if err := bosOlmayanKontrol("Go"); err != nil {
        fmt.Println("Hata:", err)
    } else {
        fmt.Println("String geçerli.")
    }
}
```

Bu örnek, Go'da hata yönetimi için `error` tipinin nasıl kullanılacağını gösterir.
