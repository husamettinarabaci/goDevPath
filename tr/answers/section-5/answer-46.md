## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımı ve Kullanımı  
#### ✅ Cevap 46: Değişken sayıda parametreli fonksiyon

Bu çözümde, değişken sayıda tamsayı parametre alan ve bunların toplamını döndüren `sumAll` adında bir fonksiyon tanımlanmıştır. Fonksiyon `main` fonksiyonundan farklı sayıda argümanla çağrılır ve sonuçlar ekrana yazdırılır.

```go
package main
import "fmt"

func sumAll(nums ...int) int {
    toplam := 0
    for _, n := range nums {
        toplam += n
    }
    return toplam
}

func main() {
    fmt.Println("Toplam 1:", sumAll(1, 2, 3))
    fmt.Println("Toplam 2:", sumAll(5, 10, 15, 20))
}
```
