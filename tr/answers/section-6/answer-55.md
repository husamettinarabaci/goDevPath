## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure ve Özyineleme  
#### ✅ Cevap 55: Fonksiyonu parametre olarak geçirme

Go'da fonksiyonlar başka fonksiyonlara parametre olarak geçirilebilir. Burada, `operate` fonksiyonu bir fonksiyon alır ve iki tamsayıya uygular.

```go
package main
import "fmt"

func operate(a, b int, fn func(int, int) int) int {
    return fn(a, b)
}

func topla(x, y int) int {
    return x + y
}

func carp(x, y int) int {
    return x * y
}

func main() {
    fmt.Println(operate(3, 4, topla)) // Çıktı: 7
    fmt.Println(operate(3, 4, carp))  // Çıktı: 12
}
```
