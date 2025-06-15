## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya Okuma  
#### ✅ Cevap 161: Dosya okuma

Go'da bir dosyayı okumak için `os` ve `io/ioutil` (veya `os` ve `io`) paketleri kullanılabilir. Bu örnekte, `example.txt` dosyasının içeriği okunup terminale yazdırılır. Hata yönetimi ile dosya yoksa veya okunamıyorsa programın çökmesi engellenir.

```go
package main
import (
    "fmt"
    "io/ioutil"
    "os"
)

func main() {
    data, err := ioutil.ReadFile("example.txt")
    if err != nil {
        fmt.Println("Dosya okuma hatası:", err)
        return
    }
    fmt.Print(string(data))
}
```
