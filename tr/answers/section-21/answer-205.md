## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: `embed` Paketi ile Dosya Gömme  
#### ✅ Cevap 205: `embed` paketi ile dosya gömme

Go'da `embed` paketi, dosyaları derleme zamanında binary'ye gömmenizi sağlar. İşte bir örnek:

`hello.txt` adında bir dosya oluşturun ve içine şunu yazın:
```
Gömülü dosyadan merhaba!
```

Daha sonra Go programınızda `embed` paketini şöyle kullanın:

```go
package main
import (
    "embed"
    "fmt"
)

//go:embed hello.txt
var helloFile string

func main() {
    fmt.Print(helloFile)
}
```

Program çalıştırıldığında, gömülü dosyanın içeriği ekrana yazdırılır.
