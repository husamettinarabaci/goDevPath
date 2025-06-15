## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: Test ve Kıyaslama  
#### ✅ Cevap 175: Kıyaslama (benchmark) yazma

Bu örnek, Go'da bir benchmark'ın nasıl yazılacağını gösterir. Benchmark fonksiyonu, string birleştirme işleminin performansını ölçmek için `b.N` döngüsünü kullanır.

`main.go`:
```go
package main

func Birlesik(a, b string) string {
    return a + b
}
```

`main_test.go`:
```go
package main
import "testing"

func BenchmarkBirlesik(b *testing.B) {
    for i := 0; i < b.N; i++ {
        _ = Birlesik("merhaba", "dünya")
    }
}
```

Benchmark'ı çalıştırmak için:

```
go test -bench .
```

Çıktıda kaç iterasyon yapıldığı ve işlem başına ortalama süre gösterilir.
