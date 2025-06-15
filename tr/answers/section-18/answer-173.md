## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: Test ve Kıyaslama  
#### ✅ Cevap 173: Hata durumlarını test etme

Bu örnek, Go'da hem normal hem de hata durumlarının nasıl test edileceğini gösterir. Bölme fonksiyonu, bölen sıfırsa hata döndürür ve test hem başarılı hem de hata durumlarını kontrol eder.

`main.go`:
```go
package main
import "errors"

func Bol(a, b int) (int, error) {
    if b == 0 {
        return 0, errors.New("sıfıra bölme hatası")
    }
    return a / b, nil
}
```

`main_test.go`:
```go
package main
import "testing"

func TestBol(t *testing.T) {
    sonuc, err := Bol(10, 2)
    if err != nil || sonuc != 5 {
        t.Errorf("Bol(10, 2) = %d, %v; beklenen 5, nil", sonuc, err)
    }

    _, err = Bol(10, 0)
    if err == nil {
        t.Errorf("Bol(10, 0) hata döndürmedi; hata bekleniyordu")
    }
}
```
