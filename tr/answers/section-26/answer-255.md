## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Arayüzler ve Structlar  
#### ✅ Cevap 255: Structlarla arayüz metotları kullanımı

Arayüzler, farklı tiplerin ortak davranışları uygulamasını sağlar. Burada `Robot` struct'ı `Speaker` arayüzünü uygular ve bir fonksiyon arayüz tipini kullanır.

```go
package main
import "fmt"

type Speaker interface {
    Speak() string
}

type Robot struct{}

func (r Robot) Speak() string {
    return "Bip bop!"
}

func duyur(s Speaker) {
    fmt.Println(s.Speak())
}

func main() {
    rob := Robot{}
    duyur(rob)
}
```
