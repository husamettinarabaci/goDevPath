## 📘 Bölüm: Dağıtım ve Araçlar
### 🔹 Kategori: Derleme ve Binary
#### ✅ Cevap 221: Go binary derleme

Bir Go programını çalıştırılabilir binary dosyasına dönüştürmek için `go build` komutu kullanılır. Varsayılan olarak, binary mevcut dizinde ve klasör adıyla aynı isimde oluşturulur.

- Çıktı dosyasının adını belirlemek için `-o` parametresi kullanılır:

```bash
go build -o benimuygulamam main.go
```

- Binary dosyası, aksi belirtilmedikçe mevcut dizinde oluşturulur.
- Örnek:

```bash
go build
```

Bu komut, mevcut dizindeki programı derler ve çalıştırılabilir bir dosya üretir.
