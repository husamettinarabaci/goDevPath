## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Context ve İptal Mekanizması  
#### ✅ Cevap 209: İptal için context kullanımı

Go'da `context` paketi, goroutine'lerin ömrünü yönetmek ve iptal sinyali göndermek için kullanılır. `context.WithCancel` fonksiyonu, bir context ve iptal fonksiyonu döndürür. İptal fonksiyonu çağrıldığında, ilgili context'i kullanan tüm goroutine'ler iptal sinyalini algılayabilir ve işlemlerini sonlandırabilir.

Aşağıdaki örnekte, uzun süren bir görev başlatılır ve kısa bir süre sonra iptal edilir:

```go
package main
import (
    "context"
    "fmt"
    "time"
)

func uzunIslem(ctx context.Context) {
    fmt.Println("Görev başladı")
    for i := 1; ; i++ {
        select {
        case <-ctx.Done():
            fmt.Println("Görev iptal edildi!")
            return
        default:
            fmt.Printf("Çalışıyor... adım %d\n", i)
            time.Sleep(500 * time.Millisecond)
        }
    }
}

func main() {
    ctx, cancel := context.WithCancel(context.Background())
    go uzunIslem(ctx)
    time.Sleep(2 * time.Second) // Görev bir süre çalışsın
    cancel() // Görevi iptal et
    time.Sleep(1 * time.Second) // İptal mesajını görmek için bekle
}
```
