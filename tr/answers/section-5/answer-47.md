## 📘 Bölüm: Fonksiyonlar I  
### 🔹 Kategori: Fonksiyon Tanımı ve Kullanımı  
#### ✅ Cevap 47: Başka bir fonksiyonu çağıran fonksiyon

Bu çözümde, bir `int` parametre alıp iki katını döndüren `double` fonksiyonu ve bu fonksiyonu çağırıp sonucu ekrana yazdıran `printDouble` fonksiyonu tanımlanmıştır. `printDouble` fonksiyonu `main` fonksiyonundan çağrılır.

```go
package main
import "fmt"

func double(n int) int {
    return n * 2
}

func printDouble(n int) {
    sonuc := double(n)
    fmt.Println("İki katı:", sonuc)
}

func main() {
    printDouble(7)
}
```
