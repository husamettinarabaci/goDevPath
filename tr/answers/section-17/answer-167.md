## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya ve Dizin İşlemleri  
#### ✅ Cevap 167: Dosya oluşturma ve silme

Go'da dosya oluşturmak ve silmek için `os.Create` ile dosya oluşturulur ve yazılır, `os.Remove` ile dosya silinir. Hata kontrolü yapılmalı ve dosya kapatılmalıdır.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    // Dosya oluştur ve yaz
    file, err := os.Create("temp.txt")
    if err != nil {
        fmt.Println("Dosya oluşturulurken hata oluştu:", err)
        return
    }
    _, err = file.WriteString("Temporary file")
    if err != nil {
        fmt.Println("Dosyaya yazılırken hata oluştu:", err)
        file.Close()
        return
    }
    file.Close()

    // Dosyayı sil
    err = os.Remove("temp.txt")
    if err != nil {
        fmt.Println("Dosya silinirken hata oluştu:", err)
        return
    }

    fmt.Println("Dosya başarıyla oluşturuldu ve silindi.")
}
```
