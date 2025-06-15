## 📘 Bölüm: Metotlar ve Arayüzler I  
### 🔹 Kategori: Metotlar  
#### ✅ Cevap 104: Birden fazla alıcı ile metot (Go'da izin verilmez)

Go'da bir metot yalnızca bir alıcıya (receiver) sahip olabilir. Birden fazla alıcı ile metot tanımlamaya çalışmak derleme hatası verir. Yanlış ve doğru kullanım örnekleri:

**Geçersiz (izin verilmez):**
```go
// Bu Go'da derlenmez
func (a A, b B) BirSeyYap() {}
```

**Doğru kullanım:**
```go
type A struct{}
type B struct{}

func (a A) BileBirlikteYap(b B) {
    // a ve b birlikte kullanılabilir
}
```

Sadece bir alıcı olabilir, diğer tipler parametre olarak geçirilir.
