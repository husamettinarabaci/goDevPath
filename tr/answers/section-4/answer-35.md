## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Terminal Girişi ve Karakter İşleme  
#### ✅ Cevap 35: Tek bir karakter okuma

Bu program, kullanıcıdan tek bir karakter ister, `bufio.Reader` ve `ReadRune` ile okur ve karakteri ekrana yazdırır. Not: Çoğu sistemde kullanıcı karakteri girdikten sonra Enter'a basmalıdır.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    reader := bufio.NewReader(os.Stdin)
    fmt.Print("Bir karakter girin: ")
    char, _, err := reader.ReadRune()
    if err != nil {
        fmt.Println("Karakter okunurken hata oluştu:", err)
        return
    }
    fmt.Printf("Girdiğiniz karakter: %c\n", char)
}
```
