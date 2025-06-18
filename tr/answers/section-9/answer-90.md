## 📘 Bölüm: Diziler ve Dilimler  
### 🔹 Kategori: Diziler ve Dilimler  
#### ✅ Cevap 90: `len` ve `cap` fonksiyonlarını kullanma

`len` fonksiyonu bir dizi veya slice'ın eleman sayısını, `cap` ise kapasitesini (slice için yeniden tahsis edilmeden önceki maksimum boyut) döndürür. Dizilerde uzunluk ve kapasite her zaman aynıdır. Slice'larda ise kapasite uzunluktan büyük olabilir ve eleman eklendikçe kapasite artabilir.

```go
package main
import "fmt"

func main() {
    arr := [5]int{1, 2, 3, 4, 5}
    slc := []int{1, 2, 3}

    fmt.Println("Dizi:", arr)
    fmt.Println("len(arr):", len(arr))
    fmt.Println("cap(arr):", cap(arr))

    fmt.Println("Slice:", slc)
    fmt.Println("len(slc):", len(slc))
    fmt.Println("cap(slc):", cap(slc))

    slc = append(slc, 4, 5, 6)
    fmt.Println("Ekledikten sonra:", slc)
    fmt.Println("len(slc):", len(slc))
    fmt.Println("cap(slc):", cap(slc))
}
```
