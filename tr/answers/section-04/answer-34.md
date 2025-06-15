## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Terminal Girişi ve String İşleme  
#### ✅ Cevap 34: Girişten boşlukları temizleme

Bu program, kullanıcıdan bir satır girişi alır, başındaki ve sonundaki boşlukları `strings.TrimSpace` fonksiyonu ile temizler ve sonucu ekrana yazdırır. Bu yöntem, Go'da kullanıcı girişini düzenlemek için kullanışlıdır.

```go
package main
import (
    "bufio"
    "fmt"
    "os"
    "strings"
)

func main() {
    reader := bufio.NewReader(os.Stdin)
    fmt.Print("Bir metin girin: ")
    input, _ := reader.ReadString('\n')
    temiz := strings.TrimSpace(input)
    fmt.Println("Temizlenmiş giriş:", temiz)
}
```
