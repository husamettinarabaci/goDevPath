## 📘 Bölüm: Diziler ve Dilimler  
### 🔹 Kategori: Dilim (Slice) Temelleri  
#### ✅ Cevap 87: Slice kopyalama

Go'da yerleşik `copy` fonksiyonu bir slice'ın elemanlarını başka bir slice'a kopyalar. Örnek:

```go
package main
import "fmt"

func main() {
    kaynak := []int{10, 20, 30, 40}
    hedef := make([]int, len(kaynak))
    copy(hedef, kaynak)
    fmt.Println("Kaynak slice:", kaynak)
    fmt.Println("Hedef slice:", hedef)
}
```

- `make([]int, len(kaynak))` ifadesi kaynak ile aynı uzunlukta yeni bir slice oluşturur.
- `copy(hedef, kaynak)` içeriği kopyalar.
- Her iki slice'ı yazdırmak kopyalamayı doğrular.
