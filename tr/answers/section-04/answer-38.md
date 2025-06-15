## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Terminal Girişi ve Sayı Ayrıştırma  
#### ✅ Cevap 38: Ondalık sayı okuma ve ayrıştırma

Bu program, kullanıcıdan ondalık bir sayı ister, girişi okur, `strconv.ParseFloat` ile `float64` tipine ayrıştırır ve hataları kullanıcıya dostça gösterir.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
    "strconv"
    "strings"
)

func main() {
    reader := bufio.NewReader(os.Stdin)
    fmt.Print("Ondalık bir sayı girin: ")
    input, _ := reader.ReadString('\n')
    input = strings.TrimSpace(input)
    num, err := strconv.ParseFloat(input, 64)
    if err != nil {
        fmt.Println("Geçersiz giriş. Lütfen geçerli bir ondalık sayı girin.")
        return
    }
    fmt.Println("Girdiğiniz sayı:", num)
}
```
