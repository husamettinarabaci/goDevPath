## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Fonksiyon Tipleri ve Callback Kullanımı  
#### ✅ Cevap 208: Fonksiyon tipleri ve callback kullanımı

Go'da fonksiyon tipleri, belirli bir imzaya sahip fonksiyonları değişken, alan veya parametre olarak tanımlamanıza olanak tanır. Callback ise bir fonksiyonun başka bir fonksiyona parametre olarak geçirilmesidir. Bu yaklaşım, kodunuzu daha esnek ve tekrar kullanılabilir hale getirir. Özellikle olay yönetimi, özel sıralama veya koleksiyon işleme gibi durumlarda yaygın olarak kullanılır.

Aşağıdaki örnekte, `Islem` adında bir fonksiyon tipi tanımlanıyor, bu tipe uygun iki fonksiyon (toplama ve çarpma) yazılıyor ve bir fonksiyona callback olarak aktarılıyor:

```go
package main
import "fmt"

// Fonksiyon tipi tanımla
 type Islem func(int, int) int

// İki fonksiyon tanımla
func topla(a, b int) int {
    return a + b
}

func carp(a, b int) int {
    return a * b
}

// Callback alan fonksiyon
func hesapla(a, b int, islem Islem) int {
    return islem(a, b)
}

func main() {
    fmt.Println("Topla:", hesapla(3, 4, topla))         // Çıktı: Topla: 7
    fmt.Println("Çarp:", hesapla(3, 4, carp))           // Çıktı: Çarp: 12
    // Anonim fonksiyon ile çıkarma işlemi
    sonuc := hesapla(10, 5, func(x, y int) int {
        return x - y
    })
    fmt.Println("Çıkar:", sonuc) // Çıktı: Çıkar: 5
}
```
