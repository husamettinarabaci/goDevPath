## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure, Özyineleme, Defer, Panic/Recover  
#### ✅ Cevap 60: Struct içinde fonksiyon alanı kullanımı

Go'da struct içinde fonksiyon alanı tanımlayarak, farklı davranışlar atayabilirsiniz. Fonksiyon alanı, fonksiyon imzası ile tanımlanır ve struct örneğine atanabilir.

```go
package main
import "fmt"

type Islemci struct {
    islem func(int, int) int
}

func main() {
    topla := func(a, b int) int { return a + b }
    carp := func(a, b int) int { return a * b }

    i1 := Islemci{islem: topla}
    i2 := Islemci{islem: carp}

    fmt.Println("Topla:", i1.islem(3, 4))      // Çıktı: 7
    fmt.Println("Çarp:", i2.islem(3, 4))       // Çıktı: 12
}
```

Burada, `Islemci` struct'ı fonksiyon alanı olarak `islem` içerir ve farklı fonksiyonlar atanarak çağrılabilir.
