## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Terminal Girişi ve Hata Yönetimi  
#### ✅ Cevap 33: Giriş hatalarını düzgün şekilde ele alma

Bu program, kullanıcıdan girdi alır, `strconv.Atoi` ile tam sayıya çevirmeye çalışır ve hata kontrolü yapar. Girdi geçerli bir tam sayı değilse, program çökmez ve kullanıcıya açıklayıcı bir hata mesajı gösterir.

```go
package main
import (
    "fmt"
    "strconv"
)

func main() {
    var input string
    fmt.Print("Bir sayı girin: ")
    _, err := fmt.Scanln(&input)
    if err != nil {
        fmt.Println("Girdi okunurken hata oluştu:", err)
        return
    }
    num, err := strconv.Atoi(input)
    if err != nil {
        fmt.Println("Geçersiz sayı. Lütfen geçerli bir tam sayı girin.")
        return
    }
    fmt.Println("Girdiğiniz sayı:", num)
}
```
