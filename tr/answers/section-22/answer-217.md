## 📘 Bölüm: Go Modülleri ve Bağımlılık Yönetimi
### 🔹 Kategori: go.mod ve Bağımlılık Yönetimi
#### ✅ Cevap 217: Özel modüller kullanma

Özel modüller, herkese açık olmayan depolarda tutulan Go modülleridir. Kullanmak için:

- `GOPRIVATE` ortam değişkenini modül yolunu kapsayacak şekilde ayarlayın (örn. `export GOPRIVATE=github.com/sirketiniz/*`).
- Git sağlayıcınızda kimlik doğrulama (SSH anahtarı veya erişim anahtarı) yapılandırmasını yapın.
- `go.mod` dosyanızda özel modülü normal bir modül gibi ekleyin:

```
require github.com/sirketiniz/ozelmodul v1.2.3
```

Go, modülü almak için kimlik bilgilerinizi kullanacaktır. Ortamınızın özel depoya erişime uygun şekilde ayarlandığından emin olun.