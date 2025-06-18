## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımlama  
#### ✅ Cevap 41: Basit bir fonksiyon tanımlama

Bu çözüm, Go'da basit bir fonksiyonun nasıl tanımlanacağını gösterir. `greet` fonksiyonu bir mesaj yazdırır ve `main` fonksiyonundan çağrılır.

```go
package main
import "fmt"

func greet() {
    fmt.Println("Hello from a function!")
}

func main() {
    greet()
}
```
