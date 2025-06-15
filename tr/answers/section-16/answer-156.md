## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ✅ Cevap 156: `sync.Cond` kullanımı

`sync.Cond`, goroutine'lerin bir koşulu beklemesini veya bu koşulun gerçekleştiğini bildirmesini sağlar. Paylaşılan kaynaklara erişimi koordine etmek için kullanılır.

```go
package main
import (
    "fmt"
    "sync"
    "time"
)

func main() {
    var (
        mu sync.Mutex
        cond = sync.NewCond(&mu)
        queue []int
    )

    // Tüketici goroutine
    go func() {
        mu.Lock()
        for len(queue) == 0 {
            cond.Wait()
        }
        fmt.Println("Tüketildi:", queue[0])
        queue = queue[1:]
        mu.Unlock()
    }()

    // Üretici goroutine
    time.Sleep(100 * time.Millisecond)
    mu.Lock()
    queue = append(queue, 42)
    cond.Signal()
    mu.Unlock()

    time.Sleep(200 * time.Millisecond)
}
```
