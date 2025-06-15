## 📘 Bölüm: Dağıtım ve Araçlar  
### 🔹 Kategori: Derleme, çapraz derleme, Docker, CI  
#### ✅ Cevap 228: `go run` ve `go install` kullanımı

`go run`, Go programlarını kaynak dosyadan derleyip hemen çalıştırır. `go install` ise binary'yi derleyip Go bin dizinine kurar.

Örnek kullanım:

```bash
go run main.go
go install
```

- `go run main.go` komutu, `main.go` dosyasını derleyip hemen çalıştırır.
- `go install` komutu, binary'yi derler ve `$GOBIN` veya `$GOPATH/bin` dizinine kurar; böylece sistem genelinde erişilebilir olur.

Hızlı testler için `go run`, tekrar kullanılabilir komutlar için `go install` kullanılır.
