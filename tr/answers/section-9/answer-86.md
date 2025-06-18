## 📘 Bölüm: Diziler ve Dilimler  
### 🔹 Kategori: Dilim (Slice) Temelleri  
#### ✅ Cevap 86: Slice'a eleman ekleme

Go dilinde bir slice'a eleman eklemek için yerleşik `append` fonksiyonu kullanılır. Örnek:

```go
package main
import "fmt"

func main() {
    sayilar := []int{1, 2, 3}
    sayilar = append(sayilar, 4, 5)
    fmt.Println(sayilar)
}
```

- `append(sayilar, 4, 5)` ifadesi 4 ve 5'i slice'ın sonuna ekler.
- Güncellenmiş slice yazdırılır.
