## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar  
### 🔹 Kategori: İdiomatik Go kodu yazma  
#### ✅ Cevap 240: İdiomatik Go kodu yazma

İdiomatik Go kodu, programların okunabilir, sürdürülebilir ve sağlam olmasını sağlayan konvansiyonlara uyar. Kısa değişken isimleri, açık hata yönetimi, kaynak temizliği için `defer` ve kalıtım yerine bileşim başlıca idiomlardandır.

```go
package main

import (
    "fmt"
    "os"
)

type Kayitci struct {
    onEk string
}

func (k Kayitci) Log(mesaj string) {
    fmt.Println(k.onEk, mesaj)
}

func main() {
    dosya, err := os.Open("veri.txt")
    if err != nil {
        fmt.Println("Hata:", err)
        return
    }
    defer dosya.Close()

    kayitci := Kayitci{onEk: "BİLGİ:"}
    kayitci.Log("Dosya başarıyla açıldı")

    // İdiomatik döngü
    for i := 0; i < 3; i++ {
        fmt.Println("Döngü", i)
    }

    // İdiomatik koşul
    if dosya != nil {
        fmt.Println("Dosya kullanıma hazır.")
    }
}
```

Go idiomlarına uymak, kodun daha okunabilir, hataya daha az açık ve sürdürülebilir olmasını sağlar.
