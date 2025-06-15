## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar
### 🔹 Kategori: Go'da singleton kalıbı
#### ✅ Cevap 233: Go'da singleton kalıbı

Singleton kalıbı, bir tipten programda yalnızca bir örnek olmasını garanti eder. Go'da idiomatik yol, thread-safe için `sync.Once` kullanmaktır.

```go
package main
import (
    "fmt"
    "sync"
)

type singleton struct {
    deger int
}

var (
    ornek *singleton
    once  sync.Once
)

func OrnekGetir() *singleton {
    once.Do(func() {
        ornek = &singleton{deger: 42}
    })
    return ornek
}

func main() {
    var wg sync.WaitGroup
    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func(id int) {
            defer wg.Done()
            s := OrnekGetir()
            fmt.Printf("Goroutine %d: %p %v\n", id, s, s.deger)
        }(i)
    }
    wg.Wait()
}
```

Bu yöntem, eşzamanlı erişimde bile yalnızca bir örnek oluşturulmasını garanti eder.
