## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar  
### 🔹 Kategori: `defer` ile kaynak temizliği  
#### ✅ Cevap 237: `defer` ile kaynak temizliği

Go'da `defer` ifadesi, bir fonksiyonun sonunda kaynakların serbest bırakılmasını sağlamak için yaygın olarak kullanılır. Bu, özellikle dosya, ağ bağlantısı gibi kapatılması gereken kaynaklar için önemlidir.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    dosya, err := os.Open("ornek.txt")
    if err != nil {
        fmt.Println("Dosya açılırken hata:", err)
        return
    }
    defer dosya.Close() // Fonksiyon bitince dosya kapanır

    // Dosya işlemleri burada yapılır
    fmt.Println("Dosya başarıyla açıldı.")
}
```

Eğer `defer dosya.Close()` kullanılmazsa, dosya açık kalabilir ve kaynak sızıntısına yol açabilir. `defer` kullanmak, fonksiyon nasıl sona ererse ersin temizlik işlemini garanti eder.
