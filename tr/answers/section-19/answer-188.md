## 📘 Bölüm: Standart Kütüphane Temelleri
### 🔹 Kategori: bufio Paketi
#### ✅ Cevap 188: `bufio` paketini kullanma

`bufio` paketi, dosyaları satır satır okumak için verimli bir yol sunar. Bu amaçla genellikle `bufio.Scanner` kullanılır.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    dosya, err := os.Open("data.txt")
    if err != nil {
        fmt.Println("Dosya açma hatası:", err)
        return
    }
    defer dosya.Close()

    scanner := bufio.NewScanner(dosya)
    for scanner.Scan() {
        fmt.Println(scanner.Text())
    }

    if err := scanner.Err(); err != nil {
        fmt.Println("Dosya okuma hatası:", err)
    }
}
```
