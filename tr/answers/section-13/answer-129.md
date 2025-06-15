## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: Dokümantasyon ve GoDoc  
#### ✅ Cevap 129: GoDoc ile dokümantasyon

GoDoc, Go kodunuzdaki özel formatlı yorumlardan dokümantasyon üretir. Paket, fonksiyon, tip veya alanın hemen üstündeki ve ilgili ismiyle başlayan yorumlar, oluşturulan dokümantasyona dahil edilir. Büyük harfle başlayan dışa açık tanımlayıcılar dokümante edilir.

```go
// mathutil paketi, matematiksel yardımcı fonksiyonlar sağlar.
package mathutil

// Add, iki tamsayının toplamını döndürür.
func Add(a, b int) int {
    return a + b
}
```

Dokümantasyonu görüntülemek için `go doc mathutil` komutunu çalıştırabilir veya çevrimiçi GoDoc görüntüleyicilerini kullanabilirsiniz. Bu, başkalarının kodunuzu ve kullanımını anlamasına yardımcı olur.
