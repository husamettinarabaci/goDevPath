## 📘 Bölüm: Dağıtım ve Araçlar  
### 🔹 Kategori: Derleme, çapraz derleme, Docker, CI  
#### ✅ Cevap 225: `go generate` kullanımı

`go generate` aracı, Go kaynak dosyalarındaki özel `//go:generate` yorum satırlarında belirtilen komutları çalıştırır. Genellikle kod üretimi veya varlık gömme için kullanılır.

Örnek:

```go
//go:generate echo "Kod üretiliyor..."
package main
import "fmt"

func main() {
    fmt.Println("Merhaba, go generate!")
}
```

Yönergeyi çalıştırmak için:

```bash
go generate
```

Bu, `//go:generate` satırındaki komutu çalıştırır. Gerçek projelerde genellikle `stringer`, `mockgen` veya varlık üreticileriyle kullanılır.
