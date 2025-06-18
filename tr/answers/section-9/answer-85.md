## 📘 Bölüm: Diziler ve Dilimler  
### 🔹 Kategori: Dilim (Slice) Temelleri  
#### ✅ Cevap 85: Slice tanımlama ve başlatma

Go dilinde bir slice, bileşik literal ile tanımlanıp başlatılabilir. Örnek:

```go
package main
import "fmt"

func main() {
    meyveler := []string{"elma", "muz", "kiraz"}
    fmt.Println(meyveler)
}
```

- `[]string{"elma", "muz", "kiraz"}` ifadesi üç elemanlı bir string slice oluşturur.
- Slice'ı yazdırmak içeriğini gösterir.
