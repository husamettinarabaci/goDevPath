## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımı ve Kullanımı  
#### ✅ Cevap 48: İsimsiz parametreli fonksiyon

Bu çözümde, iki tamsayı parametre alan ancak yalnızca ilkini kullanan `printFirst` adında bir fonksiyon tanımlanmıştır. İkinci parametre isimsiz (alt çizgi) olarak tanımlanır. Fonksiyon `main` fonksiyonundan çağrılır ve ilk parametre ekrana yazdırılır.

```go
package main
import "fmt"

func printFirst(a int, _ int) {
    fmt.Println("İlk parametre:", a)
}

func main() {
    printFirst(10, 99)
}
```
