## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Terminal Girişi ve Dilimler  
#### ✅ Cevap 39: Girişi bir slice'a okuma

Bu program, kullanıcıdan boşlukla ayrılmış değerler ister, girişi okur, `strings.Fields` ile bir slice'a böler ve sonucu ekrana yazdırır.

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
    fmt.Print("Boşlukla ayrılmış değerler girin: ")
    input, _ := reader.ReadString('\n')
    input = strings.TrimSpace(input)
    values := strings.Fields(input)
    fmt.Println("Slice:", values)
}
```
