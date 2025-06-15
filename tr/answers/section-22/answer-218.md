## 📘 Bölüm: Go Modülleri ve Bağımlılık Yönetimi
### 🔹 Kategori: go.mod ve Bağımlılık Yönetimi
#### ✅ Cevap 218: Go modüllerinde semantik versiyonlama

Semantik versiyonlama (semver), üç bölümlü bir numaralandırma şemasıdır: `MAJOR.MINOR.PATCH` (ör. `v1.2.3`).

- **MAJOR** sürüm: Geriye dönük uyumsuz API değişikliklerinde artırılır.
- **MINOR** sürüm: Geriye dönük uyumlu yeni özellikler eklendiğinde artırılır.
- **PATCH** sürüm: Geriye dönük uyumlu hata düzeltmelerinde artırılır.

Go modülleri, bağımlılık yönetimi ve uyumluluk için semantik versiyonlamayı kullanır. Sürümler her zaman `v` harfiyle başlar: `v1.0.0`, `v2.3.1`, `v0.9.5` gibi.

Semver'e uymak, modülünüzü kullananların ne zaman kırıcı değişiklikler yapıldığını anlamasını sağlar ve Go modül sistemiyle güvenli bağımlılık çözümüne olanak tanır.

**Geçerli Go modül sürümü örnekleri:**
- `v1.0.0`
- `v2.1.3`
- `v0.9.5`

Sürümleri `go.mod` dosyasında veya `go get` komutunda şu şekilde belirtebilirsiniz:

```
go get example.com/mod@v1.2.3
```

Bu, projenizde doğru sürümün kullanılmasını sağlar.