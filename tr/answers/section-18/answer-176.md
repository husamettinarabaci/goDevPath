## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: `go test` Bayraklarını Kullanma  
#### ✅ Cevap 176: `go test` bayraklarını kullanma

`go test` komutunda çeşitli bayraklar kullanarak testlerin nasıl çalıştırılacağını ve çıktının nasıl kontrol edileceğini belirleyebilirsiniz. `-v` bayrağı ayrıntılı çıktı sağlar, `-run` belirli testleri çalıştırır, `-cover` ise kod kapsamını gösterir.

Örnek test dosyası:

```go
func topla(a, b int) int {
    return a + b
}

import "testing"

func TestTopla(t *testing.T) {
    sonuc := topla(2, 3)
    if sonuc != 5 {
        t.Errorf("Beklenen 5, elde edilen %d", sonuc)
    }
}
```

Örnek komutlar:

- Tüm testleri ayrıntılı çalıştırmak için:
  ```sh
  go test -v
  ```
- Sadece `Topla` testini çalıştırmak için:
  ```sh
  go test -run=Topla
  ```
- Testleri kapsam ile çalıştırmak için:
  ```sh
  go test -cover
  ```

Bu bayraklar, hangi testlerin çalıştırılacağını, ayrıntılı çıktıyı ve kod kapsamını kontrol etmenizi sağlar.
