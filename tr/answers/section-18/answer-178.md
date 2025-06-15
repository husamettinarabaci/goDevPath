## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: Eşzamanlı kodu test etme  
#### ✅ Cevap 178: Eşzamanlı kodu test etme

Go'da eşzamanlı kodu test etmek için doğru senkronizasyon sağlanmalı ve yarış durumlarından kaçınılmalıdır. `sync.WaitGroup` genellikle goroutine'lerin tamamlanmasını beklemek için kullanılır, ayrıca `-race` bayrağı yarış durumlarını tespit etmeye yardımcı olur.

Örnek:

```go
package main
import (
    "sync"
    "testing"
)

func toplamiEszamanliHesapla(nums []int) int {
    var toplam int
    var mu sync.Mutex
    var wg sync.WaitGroup
    for _, n := range nums {
        wg.Add(1)
        go func(val int) {
            defer wg.Done()
            mu.Lock()
            toplam += val
            mu.Unlock()
        }(n)
    }
    wg.Wait()
    return toplam
}

func TestToplamiEszamanliHesapla(t *testing.T) {
    nums := []int{1, 2, 3, 4, 5}
    sonuc := toplamiEszamanliHesapla(nums)
    if sonuc != 15 {
        t.Errorf("beklenen 15, elde edilen %d", sonuc)
    }
}
```

Testi `go test -race` ile çalıştırarak yarış durumlarını kontrol edebilirsiniz.
