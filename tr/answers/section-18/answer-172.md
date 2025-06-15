## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: Test ve Kıyaslama  
#### ✅ Cevap 172: Tablo tabanlı testler

Bu örnek, Go'da tablo tabanlı testin nasıl yazılacağını gösterir. Çarpma fonksiyonu, birden fazla giriş durumu ile bir struct dizisi kullanılarak test edilir ve hatalar raporlanır.

`main.go`:
```go
package main

func Carp(a, b int) int {
    return a * b
}
```

`main_test.go`:
```go
package main
import "testing"

func TestCarp(t *testing.T) {
    testler := []struct {
        a, b   int
        sonuc  int
    }{
        {2, 3, 6},
        {0, 5, 0},
        {-1, 4, -4},
        {7, -2, -14},
    }
    for _, tt := range testler {
        got := Carp(tt.a, tt.b)
        if got != tt.sonuc {
            t.Errorf("Carp(%d, %d) = %d; beklenen %d", tt.a, tt.b, got, tt.sonuc)
        }
    }
}
```
