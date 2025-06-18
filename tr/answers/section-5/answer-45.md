## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımı ve Kullanımı  
#### ✅ Cevap 45: İsimli dönüş değerli fonksiyon

Bu çözümde, iki tamsayı parametre alan ve isimli dönüş değerleriyle toplam ve farkı döndüren `sumAndDiff` adında bir fonksiyon tanımlanmıştır. Fonksiyon `main` fonksiyonundan çağrılır ve her iki sonuç ekrana yazdırılır.

```go
package main
import "fmt"

func sumAndDiff(a int, b int) (toplam int, fark int) {
    toplam = a + b
    fark = a - b
    return
}

func main() {
    t, f := sumAndDiff(10, 4)
    fmt.Println("Toplam:", t)
    fmt.Println("Fark:", f)
}
```
