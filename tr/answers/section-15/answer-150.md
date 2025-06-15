## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine ve Kanallar  
#### ✅ Cevap 150: `select` ve `time.After` ile zaman aşımı

Bu örnekte, bir kanaldan değer beklerken `select` ve `time.After` kullanılarak zaman aşımı nasıl uygulanır gösterilmiştir. Kanal belirtilen sürede değer göndermezse zaman aşımı mesajı ekrana yazdırılır.

```go
package main
import (
    "fmt"
    "time"
)

func main() {
    ch := make(chan int)
    select {
    case v := <-ch:
        fmt.Println("Alındı:", v)
    case <-time.After(1 * time.Second):
        fmt.Println("Zaman aşımı: değer alınamadı")
    }
}
```
