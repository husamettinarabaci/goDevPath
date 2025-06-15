## 📘 Bölüm: Dağıtım ve Araçlar  
### 🔹 Kategori: Derleme, çapraz derleme, Docker, CI  
#### ✅ Cevap 222: Go programlarını çapraz derleme

Go, farklı platformlar için çapraz derlemeyi `GOOS` ve `GOARCH` ortam değişkenlerini ayarlayarak kolaylaştırır. Örneğin, macOS veya Windows'ta Linux için binary derlemek için:

```bash
GOOS=linux GOARCH=amd64 go build -o benimuygulamam-linux main.go
```

Bu komut, `main.go` dosyasından Linux 64-bit için `benimuygulamam-linux` adında bir binary oluşturur. Farklı platformlar için `GOOS` ve `GOARCH` değerlerini değiştirebilirsiniz (ör. `windows`, `darwin`, `arm64`).
