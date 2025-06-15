## 📘 Bölüm: Standart Kütüphane Temelleri
### 🔹 Kategori: sort Paketi
#### ✅ Cevap 189: `sort` paketini kullanma

`sort` paketi, yerleşik tipler ve özel tipler için slice sıralama fonksiyonları sunar. Temel tipler için `sort.Ints` ve `sort.Strings`, özel sıralama için `sort.Slice` kullanılır.

```go
package main
import (
    "fmt"
    "sort"
)

type Kisi struct {
    Isim string
    Yas  int
}

func main() {
    // Tamsayıları sırala
    sayilar := []int{5, 2, 9, 1, 7}
    sort.Ints(sayilar)
    fmt.Println("Sıralı tamsayılar:", sayilar)

    // Stringleri sırala
    kelimeler := []string{"muz", "elma", "kiraz"}
    sort.Strings(kelimeler)
    fmt.Println("Sıralı stringler:", kelimeler)

    // Struct slice'ını yaşa göre sırala
    kisiler := []Kisi{
        {Isim: "Ayşe", Yas: 30},
        {Isim: "Mehmet", Yas: 25},
        {Isim: "Zeynep", Yas: 35},
    }
    sort.Slice(kisiler, func(i, j int) bool {
        return kisiler[i].Yas < kisiler[j].Yas
    })
    fmt.Println("Yaşa göre sıralı kişiler:", kisiler)
}
```
