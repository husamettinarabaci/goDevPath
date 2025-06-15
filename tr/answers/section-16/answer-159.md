## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Deadlock ve Yarış Durumları  
#### ✅ Cevap 159: `-race` ile yarış durumu tespiti

`-race` bayrağı, Go'da çalışma zamanında veri yarışlarını tespit eden race detector'ı etkinleştirir. Aşağıda bir yarış durumu örneği ve tespit yöntemi yer alıyor.

```go
package main
import (
    "fmt"
    "sync"
)

func main() {
    var x int
    var wg sync.WaitGroup
    for i := 0; i < 1000; i++ {
        wg.Add(1)
        go func() {
            x++ // yarış durumu
            wg.Done()
        }()
    }
    wg.Wait()
    fmt.Println("Son değer:", x)
}
```

Yarış durumunu tespit etmek için şu komutu çalıştırın:

```
go run -race main.go
```

Yarış durumunu düzeltmek için mutex kullanabilirsiniz:

```go
var mu sync.Mutex
...
go func() {
    mu.Lock()
    x++
    mu.Unlock()
    wg.Done()
}()
```
