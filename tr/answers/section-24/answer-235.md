## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar
### 🔹 Kategori: Bağımlılık enjeksiyonu temelleri
#### ✅ Cevap 235: Bağımlılık enjeksiyonu temelleri

Bağımlılık enjeksiyonu, bir bileşenin ihtiyaç duyduğu bağımlılıkların doğrudan verilmesidir. Go'da bu genellikle struct alanları veya kurucu fonksiyonlar ile yapılır ve kodun test edilebilirliğini artırır.

```go
package main
import "fmt"

type Logger interface {
    Log(msg string)
}

type KonsolLogger struct{}
func (k KonsolLogger) Log(msg string) { fmt.Println(msg) }

type Servis struct {
    logger Logger
}

func YeniServis(l Logger) *Servis {
    return &Servis{logger: l}
}

func (s *Servis) BirSeyYap() {
    s.logger.Log("Bir şey yapılıyor!")
}

func main() {
    logger := KonsolLogger{}
    servis := YeniServis(logger)
    servis.BirSeyYap()
}
```

Bu yaklaşım, testlerde sahte (mock) bir logger enjekte etmeye olanak tanır ve test edilebilirliği artırır.
