## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya ve Dizin İşlemleri  
#### ✅ Cevap 168: Dizin oluşturma ve silme

Go'da dizin oluşturmak ve silmek için `os.Mkdir` ile dizin oluşturulur, `os.Create` ile dosya oluşturulur, `os.Remove`/`os.RemoveAll` ile dosya ve dizin silinir. Hata kontrolü yapılmalı ve dosya kapatılmalıdır.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    // Dizin oluştur
    err := os.Mkdir("testdir", 0755)
    if err != nil {
        fmt.Println("Dizin oluşturulurken hata oluştu:", err)
        return
    }

    // Dizin içinde dosya oluştur
    file, err := os.Create("testdir/note.txt")
    if err != nil {
        fmt.Println("Dosya oluşturulurken hata oluştu:", err)
        return
    }
    _, err = file.WriteString("Test note")
    if err != nil {
        fmt.Println("Dosyaya yazılırken hata oluştu:", err)
        file.Close()
        return
    }
    file.Close()

    // Dosyayı sil
    err = os.Remove("testdir/note.txt")
    if err != nil {
        fmt.Println("Dosya silinirken hata oluştu:", err)
        return
    }

    // Dizini sil
    err = os.Remove("testdir")
    if err != nil {
        fmt.Println("Dizin silinirken hata oluştu:", err)
        return
    }

    fmt.Println("Dizin ve dosya başarıyla oluşturuldu ve silindi.")
}
```
