## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar  
### 🔹 Kategori: Loglama için en iyi uygulamalar  
#### ✅ Cevap 239: Loglama için en iyi uygulamalar

Doğru loglama, Go uygulamalarında hata ayıklama, izleme ve bakım için çok önemlidir. Standart `log` paketi temel loglama sağlar, üçüncü parti kütüphaneler ise seviye ve yapılandırılmış çıktı gibi gelişmiş özellikler sunar.

```go
package main

import (
    "log"
    "os"
)

func main() {
    // Logları dosyaya yaz
    dosya, err := os.OpenFile("uygulama.log", os.O_CREATE|os.O_WRONLY|os.O_APPEND, 0666)
    if err != nil {
        log.Fatalf("Log dosyası açılamadı: %v", err)
    }
    log.SetOutput(dosya)
    log.SetFlags(log.Ldate | log.Ltime | log.Lshortfile)

    log.Println("BİLGİ: Uygulama başlatıldı")
    log.Println("UYARI: Bu bir uyarı mesajıdır")
    log.Println("HATA: Bu bir hata mesajıdır")
}
```

Gelişmiş loglama (seviye, yapılandırılmış log) için `logrus` veya `zap` gibi bir paket kullanılabilir:

```go
// logrus ile örnek
import log "github.com/sirupsen/logrus"

log.WithFields(log.Fields{
    "kullanici": "ayse",
    "islem": "giris",
}).Info("Kullanıcı giriş olayı")
```

Doğru loglama, uygulama akışını, hataları ve önemli olayları izlemeyi kolaylaştırır ve sorun gidermede büyük fayda sağlar.
