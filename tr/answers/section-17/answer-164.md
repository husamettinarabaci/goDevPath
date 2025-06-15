## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya ve Dizin İşlemleri  
#### ✅ Cevap 164: Dosyayı satır satır okuma

Go'da bir dosyayı satır satır okumak için `os.Open` ile dosya açılır ve `bufio.NewScanner` ile her satır üzerinde gezilir. Hata kontrolü yapılmalı ve işlem sonunda dosya kapatılmalıdır.

```go
package main

import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    file, err := os.Open("data.txt")
    if err != nil {
        fmt.Println("Dosya açılırken hata oluştu:", err)
        return
    }
    defer file.Close()

    scanner := bufio.NewScanner(file)
    for scanner.Scan() {
        fmt.Println(scanner.Text())
    }

    if err := scanner.Err(); err != nil {
        fmt.Println("Dosya okunurken hata oluştu:", err)
    }
}
```
