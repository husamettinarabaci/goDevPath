## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: Test dosyalarını organize etme  
#### ✅ Cevap 179: Test dosyalarını organize etme

Go'da test dosyaları `_test.go` ile bitmeli ve test ettikleri kodla aynı pakette yer almalıdır. Test fonksiyonları `Test` ile başlamalı ve `*testing.T` parametresi almalıdır. Paketlere göre ve büyük projelerde alt dizinler kullanarak testleri düzenlemek okunabilirliği artırır.

Örnek dizin yapısı:

```
projem/
├── main.go
├── main_test.go
├── utils/
│   ├── utils.go
│   └── utils_test.go
└── models/
    ├── user.go
    └── user_test.go
```

Örnek test fonksiyonu:

```go
// main_test.go
package main
import "testing"

func TestMainLogic(t *testing.T) {
    // test kodu buraya
}
```

Bu yapı, testlerin kodun yanında olmasını sağlar ve bakımı kolaylaştırır.
