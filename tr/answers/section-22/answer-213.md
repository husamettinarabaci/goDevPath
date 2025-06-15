## 📘 Bölüm: Go Modülleri ve Bağımlılık Yönetimi  
### 🔹 Kategori: Bağımlılık Yükseltme ve Düşürme  
#### ✅ Cevap 213: Bağımlılıkları yükseltme ve düşürme

Go modülleri, `go get` komutuna sürüm ekleyerek bağımlılıkları kolayca yükseltmenizi veya düşürmenizi sağlar.

**Adım adım örnek:**

1. Bağımlılığı ekleyin (örneğin, `github.com/fatih/color`):
   ```bash
   go get github.com/fatih/color
   ```
2. Daha yeni bir sürüme yükseltin:
   ```bash
   go get github.com/fatih/color@v1.15.0
   ```
   Bu işlem, `go.mod` ve `go.sum` dosyalarını günceller.
3. Daha eski bir sürüme düşürün:
   ```bash
   go get github.com/fatih/color@v1.10.0
   ```
   Yine, `go.mod` ve `go.sum` dosyaları güncellenir.
4. Bağımlılığı kodda kullanın:
   ```go
   package main
   import "github.com/fatih/color"
   func main() {
       color.Green("Bu yeşil bir yazıdır!")
   }
   ```

Her `go get` işleminden sonra, `go.mod` ve `go.sum` dosyalarındaki sürüm değişikliklerini kontrol edin. Böylece projenizde tam olarak istediğiniz bağımlılık sürümlerini kullanabilirsiniz.
