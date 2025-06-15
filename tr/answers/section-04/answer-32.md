## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Terminalden Girdi  
#### ✅ Cevap 32: Kullanıcı girişini sayıya çevirme

`fmt.Scanln` ile string olarak alınan kullanıcı girdisi, `strconv.Atoi` ile tamsayıya çevrilebilir. Bu örnekte kullanıcıdan sayı istenir, çevrilir ve ekrana yazdırılır.

```go
package main
import (
    "fmt"
    "strconv"
)

func main() {
    var girdi string
    fmt.Print("Bir sayı girin: ")
    fmt.Scanln(&girdi)
    sayi, err := strconv.Atoi(girdi)
    if err != nil {
        fmt.Println("Geçersiz sayı!")
        return
    }
    fmt.Println("Girilen sayı:", sayi)
}
```
