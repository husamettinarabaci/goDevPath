## 📘 Bölüm: Go Modülleri ve Bağımlılık Yönetimi  
### 🔹 Kategori: Modül Bakımı  
#### ✅ Cevap 214: `go mod tidy` kullanımı

`go mod tidy` komutu, `go.mod` ve `go.sum` dosyalarınızın kodunuzda kullanılan bağımlılıklarla uyumlu olmasını sağlar. Kullanılmayan bağımlılıkları kaldırır, eksik olanları ekler.

**Adım adım örnek:**

1. Kodunuza bir import ekleyip `go get` çalıştırmazsanız:
   ```go
   import "github.com/fatih/color"
   ```
   `go mod tidy` çalıştırıldığında bu bağımlılık `go.mod` ve `go.sum` dosyalarına eklenir.
2. Kodunuzdan bir paketi tamamen kaldırırsanız, `go mod tidy` ile bu bağımlılık modül dosyalarından silinir.
3. Kullanım:
   ```bash
   go mod tidy
   ```

Modül dosyalarını düzenli tutmak, tekrar üretilebilir derlemeler, gereksiz bağımlılıkların önlenmesi ve projenin temiz kalması için önemlidir.
