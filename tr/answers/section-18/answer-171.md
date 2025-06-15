## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: Test ve Kıyaslama  
#### ✅ Cevap 171: `testing` paketi ile temel test yazma

Bu örnek, basit bir fonksiyon ve ona karşılık gelen testin Go'nun `testing` paketiyle nasıl yazılacağını gösterir. Test, toplama fonksiyonunun doğru sonucu döndürüp döndürmediğini kontrol eder ve hata varsa bildirir.

`main.go`:
```go
package main

func Topla(a, b int) int {
    return a + b
}
```

`main_test.go`:
```go
package main
import "testing"

func TestTopla(t *testing.T) {
    sonuc := Topla(2, 3)
    beklenen := 5
    if sonuc != beklenen {
        t.Errorf("Topla(2, 3) = %d; beklenen %d", sonuc, beklenen)
    }
}
```
