## 📘 Bölüm: Diziler ve Dilimler  
### 🔹 Kategori: Diziler ve Dilimler  
#### ✅ Cevap 82: Dizi elemanlarına erişim ve değiştirme

Go'da bir dizinin elemanına erişmek veya onu değiştirmek için indeks kullanılır (indeksler 0'dan başlar). Bu örnekte, bir tamsayı dizisinin üçüncü elemanını ekrana yazdırıp, sonra bu elemanı güncelliyoruz.

```go
package main
import "fmt"

func main() {
    arr := [5]int{10, 20, 30, 40, 50}
    fmt.Println("Orijinal üçüncü eleman:", arr[2]) // 2. indeks üçüncü elemandır
    arr[2] = 99 // Üçüncü elemanı değiştir
    fmt.Println("Güncellenmiş dizi:", arr)
}
```
