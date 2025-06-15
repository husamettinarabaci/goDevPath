## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine, WaitGroup, kanal kullanımı  
#### ✅ Cevap 142: Bir goroutine başlatma

Bir fonksiyon çağrısının başına `go` anahtar kelimesi ekleyerek bir goroutine başlatabilirsiniz. Bu, fonksiyonun programınızın geri kalanıyla eşzamanlı çalışmasını sağlar.

```go
package main
import (
    "fmt"
    "time"
)

func isci() {
    fmt.Println("İşçi goroutine başladı")
    time.Sleep(50 * time.Millisecond)
    fmt.Println("İşçi goroutine bitti")
}

func main() {
    go isci()
    fmt.Println("Main fonksiyonu devam ediyor...")
    time.Sleep(100 * time.Millisecond) // Goroutine'in bitmesini bekle
    fmt.Println("Main fonksiyonu bitti.")
}
```
