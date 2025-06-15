## 📘 Bölüm: Dağıtım ve Araçlar
### 🔹 Kategori: Go projeleri için sürekli entegrasyon
#### ✅ Cevap 230: Go projeleri için sürekli entegrasyon (CI)

Sürekli entegrasyon (CI), Go projenizdeki her değişiklikte testleri ve kod kontrollerini otomatikleştirir. Aşağıda GitHub Actions ile örnek bir kurulum verilmiştir:

**Örnek: `.github/workflows/go.yml`**

```yaml
name: Go CI
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Go kurulumu
        uses: actions/setup-go@v5
        with:
          go-version: '1.21'
      - name: Bağımlılıkları yükle
        run: go mod tidy
      - name: Testleri çalıştır
        run: go test ./...
      - name: Format kontrolü
        run: go fmt ./...
```

**Açıklama:**
- Bu iş akışı, `main` dalına yapılan her push veya pull request'te çalışır.
- Kodunuzu indirir, Go ortamını kurar, bağımlılıkları yükler, testleri ve format kontrolünü çalıştırır.
- CI, hataları erken yakalamaya ve kod kalitesini korumaya yardımcı olur.
