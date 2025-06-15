## 📘 Bölüm: Go Modülleri ve Bağımlılık Yönetimi  
### 🔹 Kategori: Go Modül Temelleri  
#### ✅ Cevap 211: Go modülü başlatma

Go modülleri, modern Go projelerinde bağımlılık yönetiminin standart yoludur. `go mod init` komutu, modül yolunu ve bağımlılıkları takip eden bir `go.mod` dosyası oluşturur.

**Adım adım örnek:**

1. Yeni bir dizin oluşturun ve içine girin:
   ```bash
   mkdir projem
   cd projem
   ```
2. Go modülünü başlatın:
   ```bash
   go mod init ornek.com/projem
   ```
   Bu işlem sonucunda aşağıdaki gibi bir `go.mod` dosyası oluşur:
   ```
   module ornek.com/projem

   go 1.21
   ```
3. `main.go` dosyasını oluşturun:
   ```go
   package main
   import "fmt"
   func main() {
       fmt.Println("Merhaba, Go Modülleri!")
   }
   ```
4. Programı çalıştırın:
   ```bash
   go run main.go
   ```

`go.mod` dosyası, modül yolunu ve Go sürümünü tanımlar; bağımlılıklar eklendikçe onları da listeler. Tekrar üretilebilir derlemeler ve bağımlılık yönetimi için gereklidir.
