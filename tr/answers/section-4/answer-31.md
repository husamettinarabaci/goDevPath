## 📘 Bölüm: Girdi/Çıktı Temelleri  
### 🔹 Kategori: Terminalden Girdi  
#### ✅ Cevap 31: `fmt.Scanln` ile terminalden giriş okuma

`fmt.Scanln` fonksiyonu ile terminalden bir satır girdi okuyabilirsiniz. Bu örnekte kullanıcıdan metin istenir, okunur ve tekrar yazdırılır.

```go
package main
import "fmt"

func main() {
    var girdi string
    fmt.Print("Bir metin girin: ")
    fmt.Scanln(&girdi)
    fmt.Println("Girdiğiniz:", girdi)
}
```
