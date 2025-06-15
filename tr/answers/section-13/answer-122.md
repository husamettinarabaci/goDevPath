## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: Standart Kütüphane Paketlerini İçe Aktarma  
#### ✅ Cevap 122: Standart kütüphane paketlerini içe aktarma

Go'da standart bir kütüphane paketini kullanmak için, dosyanın başında paketi içe aktarın ve dışa açık fonksiyonlarını çağırın. Burada, `math` paketi ile karekök hesaplanıyor.

```go
package main

import (
    "fmt"
    "math"
)

func main() {
    sonuc := math.Sqrt(16)
    fmt.Println(sonuc)
}
```

Bu program, `math` paketini içe aktarır ve `math.Sqrt` fonksiyonu ile 16'nın karekökünü hesaplayıp sonucu ekrana yazdırır.
