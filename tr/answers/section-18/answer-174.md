## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: Test ve Kıyaslama  
#### ✅ Cevap 174: Test kapsamı araçlarını kullanma

Bu örnek, Go'da test kapsamının nasıl ölçüleceğini gösterir. `go test -cover` komutu, testler tarafından kapsanan kod yüzdesini raporlar.

`main.go`:
```go
package main

func Cikar(a, b int) int {
    return a - b
}
```

`main_test.go`:
```go
package main
import "testing"

func TestCikar(t *testing.T) {
    sonuc := Cikar(5, 3)
    beklenen := 2
    if sonuc != beklenen {
        t.Errorf("Cikar(5, 3) = %d; beklenen %d", sonuc, beklenen)
    }
}
```

Test kapsamını ölçmek için şu komutu çalıştırın:

```
go test -cover
```

Çıktı şöyle olacaktır:

```
PASS
coverage: 100.0% of statements
```

Kapsam yüzdesi, testlerinizin kodunuzun ne kadarını çalıştırdığını gösterir. Yüksek kapsam, daha fazla kodun test edildiği anlamına gelir.
