## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımı ve Kullanımı  
#### ✅ Cevap 49: Pointer döndüren fonksiyon

Bu çözümde, bir tamsayı parametre alıp bu tamsayının pointer'ını döndüren `intPointer` adında bir fonksiyon tanımlanmıştır. Fonksiyon `main` fonksiyonundan çağrılır ve dönen pointer'ın gösterdiği değer ekrana yazdırılır.

```go
package main
import "fmt"

func intPointer(n int) *int {
    return &n
}

func main() {
    ptr := intPointer(42)
    fmt.Println("Değer:", *ptr)
}
```
