## 📘 Bölüm: Dağıtım ve Araçlar  
### 🔹 Kategori: Derleme, çapraz derleme, Docker, CI  
#### ✅ Cevap 224: Binary içine varlık gömme

Go 1.16+ ile gelen `embed` paketi, statik dosyaları binary'ye gömmeyi sağlar. Özel bir yorum satırı ile dosya belirtilir ve `embed.FS` veya `string`/`[]byte` tipinde bir değişken tanımlanır.

Örneğin, `mesaj.txt` adında bir dosyanız olduğunu varsayalım:

```go
package main
import (
    "embed"
    "fmt"
)

//go:embed mesaj.txt
var mesaj string

func main() {
    fmt.Println(mesaj)
}
```

Bu program derlenip çalıştırıldığında, `mesaj.txt` dosyasının içeriği ekrana yazdırılır; dosya çalışma anında mevcut olmasa bile.
