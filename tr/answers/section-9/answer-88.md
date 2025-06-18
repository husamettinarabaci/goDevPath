## 📘 Bölüm: Diziler ve Dilimler  
### 🔹 Kategori: Dilim (Slice) Temelleri  
#### ✅ Cevap 88: Slice ve altında yatan diziler

Go'da slice'lar altında yatan diziyi paylaşır. Slice üzerinde yapılan değişiklikler diziyi de etkiler. Örnek:

```go
package main
import "fmt"

func main() {
    dizi := [5]int{1, 2, 3, 4, 5}
    s := dizi[1:4] // 2. ile 4. elemanlar: 2, 3, 4
    s[0] = 99      // Slice'ın ilk elemanını değiştir
    fmt.Println("Dizi:", dizi)
    fmt.Println("Slice:", s)
}
```

- `s[0]`'ı değiştirmek, `dizi[1]`'i de değiştirir çünkü slice aynı altında yatan diziyi kullanır.
- Çıktı:
  - `Dizi: [1 99 3 4 5]`
  - `Slice: [99 3 4]`
