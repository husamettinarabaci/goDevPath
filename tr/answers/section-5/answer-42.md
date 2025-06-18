## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımı ve Kullanımı  
#### ✅ Cevap 42: Parametreli ve dönüş değerli fonksiyon

Bu çözümde, iki tamsayı parametre alan ve bunların toplamını döndüren `add` adında bir fonksiyon tanımlanmıştır. Fonksiyon `main` fonksiyonundan çağrılır ve sonuç ekrana yazdırılır.

```go
package main
import "fmt"

func add(a int, b int) int {
    return a + b
}

func main() {
    result := add(3, 5)
    fmt.Println("Toplam:", result)
}
```
