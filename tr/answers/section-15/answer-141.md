## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine, WaitGroup, kanal kullanımı  
#### ✅ Cevap 141: Goroutine'lere giriş

Goroutine, Go çalışma zamanı tarafından yönetilen hafif bir iş parçacığıdır. Bir fonksiyon çağrısının başına `go` anahtar kelimesi ekleyerek bir goroutine başlatabilirsiniz. Goroutine'in tamamlanması için `main` fonksiyonunda `time.Sleep` kullanılabilir.

```go
package main
import (
    "fmt"
    "time"
)

func selamla() {
    fmt.Println("Goroutine'den merhaba!")
}

func main() {
    go selamla()
    time.Sleep(100 * time.Millisecond) // Goroutine'in çalışması için zaman tanı
    fmt.Println("Main fonksiyonu bitti.")
}
```
