## 📘 Bölüm: Go Modülleri ve Bağımlılık Yönetimi  
### 🔹 Kategori: Bağımlılık Ekleme  
#### ✅ Cevap 212: `go get` ile bağımlılık ekleme

Go projelerinde harici bağımlılık eklemek için `go get` komutu kullanılır. Bu komut, paketi indirir, `go.mod` ve `go.sum` dosyalarını günceller ve paketin içe aktarılmasını sağlar.

**Adım adım örnek:**

1. Go modülünü başlatın (henüz yapılmadıysa):
   ```bash
   go mod init ornek.com/projem
   ```
2. Bağımlılığı ekleyin (örneğin, `github.com/fatih/color`):
   ```bash
   go get github.com/fatih/color
   ```
   Bu işlem, `go.mod` ve `go.sum` dosyalarını günceller.
3. Paketi kodunuzda kullanın:
   ```go
   package main
   import "github.com/fatih/color"
   func main() {
       color.Red("Bu kırmızı bir yazıdır!")
   }
   ```
4. Programı çalıştırın:
   ```bash
   go run main.go
   ```

`go get` komutu çalıştırıldıktan sonra, `go.mod` dosyanızda yeni bağımlılık satırı eklenir ve `go.sum` dosyasında doğrulama için özetler tutulur.
