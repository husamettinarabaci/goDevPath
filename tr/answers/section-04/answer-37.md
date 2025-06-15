## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Terminal Girişi ve Kullanıcı İstemleri  
#### ✅ Cevap 37: İstemli giriş okuma

Bu program, kullanıcıya bir istem gösterir, bir satır giriş alır ve girilen veriyi ekrana yazdırır. Esnek giriş işlemleri için `bufio.Reader` kullanılmıştır.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
)

func main() {
    reader := bufio.NewReader(os.Stdin)
    fmt.Print("Lütfen adınızı girin: ")
    input, _ := reader.ReadString('\n')
    fmt.Printf("Girdiğiniz: %s", input)
}
```
