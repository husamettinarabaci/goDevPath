## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Terminal Girişi ve EOF Yönetimi  
#### ✅ Cevap 36: EOF'a kadar giriş okuma

Bu program, terminalden EOF'a kadar satır satır giriş alır, her satırı bir slice'a ekler ve sonunda tüm satırları ekrana yazdırır. Satır bazlı giriş için `bufio.Scanner` kullanılır ve EOF otomatik olarak algılanır.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    var satirlar []string
    scanner := bufio.NewScanner(os.Stdin)
    fmt.Println("Satırları girin (bitirmek için Ctrl+D):")
    for scanner.Scan() {
        satirlar = append(satirlar, scanner.Text())
    }
    if err := scanner.Err(); err != nil {
        fmt.Println("Giriş okunurken hata oluştu:", err)
        return
    }
    fmt.Println("\nGirilen tüm satırlar:")
    for _, satir := range satirlar {
        fmt.Println(satir)
    }
}
```
