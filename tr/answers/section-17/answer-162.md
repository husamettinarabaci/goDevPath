## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya ve Dizin İşlemleri  
#### ✅ Cevap 162: Dosyaya yazma

Go'da bir dosyaya yazmak için `os.Create` ile dosya oluşturulur veya var olan dosya üzerine yazılır, ardından `WriteString` veya `ioutil.WriteFile` ile veri yazılır. Hata kontrolü yapılmalı ve işlem sonunda dosya kapatılmalıdır.

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    file, err := os.Create("output.txt")
    if err != nil {
        fmt.Println("Dosya oluşturulurken hata oluştu:", err)
        return
    }
    defer file.Close()

    _, err = file.WriteString("Hello, Go file!")
    if err != nil {
        fmt.Println("Dosyaya yazılırken hata oluştu:", err)
        return
    }

    fmt.Println("Dosya başarıyla yazıldı.")
}
```
