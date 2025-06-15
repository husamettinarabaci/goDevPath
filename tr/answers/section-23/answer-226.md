## 📘 Bölüm: Dağıtım ve Araçlar  
### 🔹 Kategori: Derleme, çapraz derleme, Docker, CI  
#### ✅ Cevap 226: `go fmt` ve `goimports` kullanımı

`go fmt`, Go kaynak dosyalarını standart biçim kurallarına göre otomatik olarak biçimlendirir. `goimports` ise kodu biçimlendirmenin yanı sıra import satırlarını da ekler veya kaldırır.

Örnek kullanım:

```bash
go fmt ./...
goimports -w .
```

- `go fmt ./...` mevcut modüldeki tüm Go dosyalarını biçimlendirir.
- `goimports -w .` tüm Go dosyalarını biçimlendirir ve importları günceller.

`goimports`, özellikle importları temiz ve güncel tutmak için faydalıdır.
