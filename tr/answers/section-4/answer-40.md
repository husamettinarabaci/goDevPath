## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Dosya Girişi  
#### ✅ Cevap 40: Dosyadan giriş okuma

Bu program, bir dosyayı (ör. `input.txt`) açar, içeriğini satır satır `bufio.Scanner` ile okur ve her satırı ekrana yazdırır. Dosya açma veya okuma hatalarını kullanıcıya gösterir.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    file, err := os.Open("input.txt")
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
