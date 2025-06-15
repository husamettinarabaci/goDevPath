## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ✅ Cevap 155: `sync.Once` kullanımı

`sync.Once`, bir fonksiyonun birden fazla goroutine tarafından çağrılsa bile yalnızca bir kez çalıştırılmasını sağlar. Bu, tek seferlik başlatma işlemleri için kullanışlıdır.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    var once sync.Once
    var wg sync.WaitGroup

    initialize := func() {
        fmt.Println("Başlatıldı!")
    }

    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func() {
            once.Do(initialize)
            wg.Done()
        }()
    }
    wg.Wait()
}
```
