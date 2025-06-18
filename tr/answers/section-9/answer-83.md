## 📘 Bölüm: Diziler ve Dilimler  
### 🔹 Kategori: Dizi Temelleri  
#### ✅ Cevap 83: `for` ile dizilerde yineleme

Go dilinde bir dizi üzerinde yineleme yapmak için indeksli `for` döngüsü veya `range` anahtar kelimesi kullanılabilir. Her iki yöntemin örneği aşağıdadır:

```go
package main
import "fmt"

func main() {
    arr := [5]int{1, 2, 3, 4, 5}
    // İndeks ile
    for i := 0; i < len(arr); i++ {
        fmt.Println(arr[i])
    }
    // range ile
    for _, v := range arr {
        fmt.Println(v)
    }
}
```

- İlk döngüde indeks ile her elemana erişilir.
- İkinci döngüde `range` ile doğrudan değerlere erişilir.
