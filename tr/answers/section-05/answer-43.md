## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımı ve Kullanımı  
#### ✅ Cevap 43: `main` fonksiyonundan başka bir fonksiyon çağırma

Bu çözümde, `greet` adında bir fonksiyon tanımlanır ve bir mesaj yazdırılır. `main` fonksiyonunda `greet` fonksiyonu çağrılarak, Go'da kullanıcı tanımlı bir fonksiyonun nasıl çağrılacağı gösterilmiştir.

```go
package main
import "fmt"

func greet() {
    fmt.Println("Fonksiyondan merhaba!")
}

func main() {
    greet()
}
```
