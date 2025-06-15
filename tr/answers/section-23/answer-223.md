## 📘 Bölüm: Dağıtım ve Araçlar  
### 🔹 Kategori: Derleme, çapraz derleme, Docker, CI  
#### ✅ Cevap 223: Ortam değişkenlerini kullanma

Go'da ortam değişkenlerini okumak için `os` paketi kullanılır. `os.Getenv` fonksiyonu, bir ortam değişkeninin değerini döndürür. Programı çalıştırmadan önce terminalde değişkeni ayarlayın.

```go
package main
import (
    "fmt"
    "os"
)

func main() {
    isim := os.Getenv("ISIM")
    if isim == "" {
        fmt.Println("ISIM ortam değişkeni ayarlı değil.")
    } else {
        fmt.Printf("Merhaba, %s!\n", isim)
    }
}
```

Terminalde ayarlayıp çalıştırmak için:

```bash
export ISIM=GoDev
go run main.go
```
