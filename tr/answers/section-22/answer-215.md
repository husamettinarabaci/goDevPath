## 📘 Bölüm: Go Modülleri ve Bağımlılık Yönetimi  
### 🔹 Kategori: Vendor Dizinleri  
#### ✅ Cevap 215: `go mod vendor` kullanımı

`go mod vendor` komutu, projenizdeki tüm bağımlılıkları yerel bir `vendor` dizinine kopyalar. Böylece projeyi internetten bağımlılık indirmeden derleyebilirsiniz. Bu, tekrarlanabilir derlemeler, çevrimdışı geliştirme veya kurumsal gereksinimler için faydalıdır.

**Adım adım örnek:**

1. Bir bağımlılık ekleyin (örneğin, `github.com/fatih/color`):
   ```bash
   go get github.com/fatih/color
   ```
2. Vendor dizinini oluşturun:
   ```bash
   go mod vendor
   ```
   Bu işlem, tüm bağımlılıkları `vendor/` klasörüne kopyalar.
3. Projeyi vendor bağımlılıklarıyla derleyin:
   ```bash
   go build -mod=vendor
   ```

Vendor kullanımı, tüm bağımlılıkların yerel olarak mevcut olmasını istediğinizde; örneğin CI/CD süreçlerinde, internet erişimi olmayan ortamlarda veya kurumsal politika gereği tercih edilir.
