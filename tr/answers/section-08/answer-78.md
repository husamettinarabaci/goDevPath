## 📘 Bölüm: Structlar  
### 🔹 Kategori: Structlarda Sıfır Değerler  
#### ✅ Cevap 78: Structlarda sıfır değerler

Go'da struct alanları açıkça başlatılmazsa otomatik olarak sıfır değerler atanır. Örneğin, string için `""`, int için `0` atanır.

```go
package main
import "fmt"

type User struct {
    name string
    age  int
}

func main() {
    var u User
    fmt.Println("İsim:", u.name) // boş string
    fmt.Println("Yaş:", u.age)   // 0
}
```
