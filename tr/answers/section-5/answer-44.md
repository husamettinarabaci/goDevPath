## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımı ve Kullanımı  
#### ✅ Cevap 44: Birden fazla değer döndüren fonksiyon

Bu çözümde, iki tamsayı parametre alan ve hem toplamını hem de çarpımını döndüren `sumAndProduct` adında bir fonksiyon tanımlanmıştır. Fonksiyon `main` fonksiyonundan çağrılır ve her iki sonuç ekrana yazdırılır.

```go
package main
import "fmt"

func sumAndProduct(a int, b int) (int, int) {
    return a + b, a * b
}

func main() {
    toplam, carpim := sumAndProduct(4, 6)
    fmt.Println("Toplam:", toplam)
    fmt.Println("Çarpım:", carpim)
}
```
