## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya ve Dizin İşlemleri  
#### ✅ Cevap 163: Dosyaya ekleme

Go'da bir dosyaya ekleme yapmak için `os.OpenFile` fonksiyonu `os.O_APPEND|os.O_CREATE|os.O_WRONLY` bayraklarıyla kullanılır. Bu, dosyayı ekleme modunda açar, yoksa oluşturur ve yazmaya izin verir. Hata kontrolü yapılmalı ve işlem sonunda dosya kapatılmalıdır.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    file, err := os.OpenFile("log.txt", os.O_APPEND|os.O_CREATE|os.O_WRONLY, 0644)
    if err != nil {
        fmt.Println("Dosya açılırken hata oluştu:", err)
        return
    }
    defer file.Close()

    _, err = file.WriteString("New log entry\n")
    if err != nil {
        fmt.Println("Dosyaya ekleme yapılırken hata oluştu:", err)
        return
    }

    fmt.Println("Log kaydı eklendi.")
}
```
