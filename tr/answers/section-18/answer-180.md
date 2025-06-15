## 📘 Bölüm: Test ve Kıyaslama  
### 🔹 Kategori: Test için en iyi uygulamalar  
#### ✅ Cevap 180: Test için en iyi uygulamalar

Go'da test yazarken en iyi uygulamalar şunlardır:

- **Test izolasyonu:** Her test bağımsız olmalı, paylaşılan duruma bağlı olmamalıdır.
- **Açık adlandırma:** Test fonksiyonları açıklayıcı olmalıdır (ör. `TestToplama`).
- **Tekrarlanabilirlik:** Testler her çalıştırmada aynı sonucu vermelidir.
- **`t.Helper()` kullanımı:** Yardımcı fonksiyonlarda hata raporlamasını iyileştirir.
- **Tablo tabanlı testler:** Benzer mantıklar için slice ile test senaryoları kullanın.
- **Hataları kontrol edin:** Testlerde her zaman hataları kontrol edin ve yönetin.
- **Testleri koda yakın tutun:** Testler, test edilen kodla aynı pakette olmalıdır.

İyi bir test örneği:

```go
func TestToplama(t *testing.T) {
    sonuc := Toplama(2, 3)
    beklenen := 5
    if sonuc != beklenen {
        t.Errorf("Toplama(2, 3) = %d; beklenen %d", sonuc, beklenen)
    }
}
```

Kötü bir test örneği:

```go
func TestToplama(t *testing.T) {
    if Toplama(2, 3) != 5 {
        // hata mesajı yok, hata ayıklamak zor
    }
}
```

İyi testler açık, izole ve başarısız olduğunda faydalı geri bildirim sağlar.
