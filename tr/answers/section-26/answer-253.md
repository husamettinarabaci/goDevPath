## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Metotlar  
#### ✅ Cevap 253: Pointer alıcı ile metotlar

Pointer alıcı ile tanımlanan metotlar, struct'ın alanlarını doğrudan değiştirebilir. Burada `Counter` struct'ı ve değerini artıran `Increment` metodu tanımlanır.

```go
package main
import "fmt"

type Counter struct {
    Value int
}

func (c *Counter) Increment() {
    c.Value++
}

func main() {
    cnt := Counter{Value: 0}
    cnt.Increment()
    fmt.Println("Değer:", cnt.Value)
}
```
