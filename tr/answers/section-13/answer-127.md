## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: Dışa Açık ve Kapalı Tanımlayıcılar  
#### ✅ Cevap 127: Dışa açık ve kapalı tanımlayıcılar

Go'da büyük harfle başlayan tanımlayıcılar dışa açıktır (public) ve diğer paketlerden erişilebilir. Küçük harfle başlayanlar ise dışa kapalıdır (private) ve sadece aynı paket içinde kullanılabilir. Örnek:

```go
// mypkg/mypkg.go
package mypkg

var ExportedVar = "Ben dışa açığım!"
var unexportedVar = "Ben dışa kapalıyım!"
```

```go
// main.go
package main

import (
    "fmt"
    "mypkg"
)

func main() {
    fmt.Println(mypkg.ExportedVar)      // Erişilebilir
    // fmt.Println(mypkg.unexportedVar) // Derleme hatası: unexportedVar erişilemez
}
```

Sadece `ExportedVar` değişkenine erişilebilir. `unexportedVar` değişkenine erişmeye çalışmak derleme hatası verir.
