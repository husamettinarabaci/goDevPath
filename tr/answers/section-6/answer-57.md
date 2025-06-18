## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure ve Özyineleme  
#### ✅ Cevap 57: Go fonksiyonlarında özyineleme

Özyineleme, bir fonksiyonun kendini çağırarak problemi çözmesidir. Burada, `factorial` fonksiyonu kendini çağırarak bir sayının faktöriyelini hesaplar.

```go
package main
import "fmt"

func factorial(n int) int {
    if n == 0 {
        return 1
    }
    return n * factorial(n-1)
}

func main() {
    fmt.Println(factorial(5)) // Çıktı: 120
}
```
