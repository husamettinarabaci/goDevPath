## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: Kodu Paketlerle Organize Etme  
#### ✅ Cevap 130: Kodun paketlerle organize edilmesi

Kodu paketlere ayırmak, modülerlik ve sürdürülebilirlik sağlar. Go'da her paket için ayrı klasörler oluşturabilirsiniz. Örneğin:

`utils/utils.go`:
```go
package utils

// Greet, bir karşılama mesajı döndürür.
func Greet(name string) string {
    return "Merhaba, " + name
}
```

`main.go`:
```go
package main

import (
    "fmt"
    "modulunuz/utils"
)

func main() {
    msg := utils.Greet("GoDevPath")
    fmt.Println(msg)
}
```

`modulunuz` kısmını kendi modül adınızla değiştirin. Bu yapı, kodunuzu yeniden kullanmanıza ve projenizi düzenli tutmanıza olanak tanır.
