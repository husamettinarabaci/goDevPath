## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: Testlerde mock kullanımı  
#### ✅ Cevap 177: Testlerde mock kullanımı

Mock kullanımı, dış kaynaklara bağımlı kodu test ederken bu kaynakları kontrollü uygulamalarla değiştirmenizi sağlar. Go'da genellikle bir arayüz tanımlanır ve test için bir mock uygulama sağlanır.

Örnek:

```go
package main
import "testing"

// Bağımlılık arayüzü
type Greeter interface {
    Greet(name string) string
}

// Gerçek uygulama
type RealGreeter struct{}
func (g RealGreeter) Greet(name string) string {
    return "Hello, " + name
}

// Test için mock uygulama
type MockGreeter struct{}
func (g MockGreeter) Greet(name string) string {
    return "Merhaba, mock " + name
}

func GreetUser(g Greeter, name string) string {
    return g.Greet(name)
}

func TestGreetUser(t *testing.T) {
    mock := MockGreeter{}
    result := GreetUser(mock, "Go")
    if result != "Merhaba, mock Go" {
        t.Errorf("beklenmeyen sonuç: %s", result)
    }
}
```

Bu test, gerçek uygulamaya bağlı kalmadan `GreetUser` fonksiyonunun davranışını mock ile doğrular.
