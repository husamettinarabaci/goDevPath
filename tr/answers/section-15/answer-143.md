## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine, WaitGroup, kanal kullanımı  
#### ✅ Cevap 143: `WaitGroup` ile senkronizasyon

`sync.WaitGroup` tipi, birden fazla goroutine'in tamamlanmasını beklemenizi sağlar. Sayaç `Add` ile artırılır, her goroutine'de `Done` çağrılır ve `main` fonksiyonunda `Wait` ile tümünün bitmesi beklenir.

```go
package main
import (
    "fmt"
    "sync"
)

func isci(id int, wg *sync.WaitGroup) {
    defer wg.Done()
    fmt.Printf("İşçi %d bitti\n", id)
}

func main() {
    var wg sync.WaitGroup
    for i := 1; i <= 2; i++ {
        wg.Add(1)
        go isci(i, &wg)
    }
    wg.Wait()
    fmt.Println("Tüm işçiler tamamlandı.")
}
```
