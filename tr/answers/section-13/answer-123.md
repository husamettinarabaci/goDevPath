## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: Üçüncü Parti Paketleri İçe Aktarma  
#### ✅ Cevap 123: Üçüncü parti paketleri içe aktarma

Go'da üçüncü parti bir paketi kullanmak için önce `go get` ile yükleyin, ardından içe aktararak fonksiyonlarını kullanın. Burada, `github.com/fatih/color` paketi ile renkli metin yazdırıyoruz.

Önce paketi yükleyin:

```sh
go get github.com/fatih/color
```

Daha sonra kodunuzda kullanın:

```go
package main

import (
    "github.com/fatih/color"
)

func main() {
    color.Cyan("Bu bir camgöbeği mesajdır!")
}
```

Bu program, üçüncü parti `color` paketi ile camgöbeği renkte bir mesajı ekrana yazdırır.
