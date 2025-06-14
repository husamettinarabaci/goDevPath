## 📘 Bölüm: Değişkenler, Sabitler ve Tipler  
### 🔹 Kategori: Sabitler ve iota  
#### ✅ Cevap 13: Sabit tanımlama ve `iota` kullanımı

Go'da sabitler `const` anahtar kelimesiyle tanımlanır. `iota` ise bir sabit bloğunda otomatik artan değerler üretmek için kullanılır. Aşağıda bir örnek yer almaktadır:

```go
package main
import "fmt"
func main() {
    const Pi = 3.14
    const (
        A = iota // 0
        B        // 1
        C        // 2
    )
    fmt.Println("Pi:", Pi)
    fmt.Println("A:", A, "B:", B, "C:", C)
}
```

Bu program, bir sabitin nasıl tanımlanacağını ve `iota` ile artan değerlerin nasıl oluşturulacağını göstermektedir.
