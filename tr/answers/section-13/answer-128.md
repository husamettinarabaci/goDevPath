## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: İçe Aktarmada Takma Ad Kullanımı  
#### ✅ Cevap 128: İçe aktarmada takma ad kullanımı

Go'da bir paketi içe aktarırken takma ad (alias) verilebilir. Bu, paket adını kısaltmak veya isim çakışmalarını önlemek için kullanılır.

```go
package main

import f "fmt"

func main() {
    f.Println("Takma ad ile merhaba!")
}
```

Burada, `fmt` paketi `f` takma adıyla içe aktarılmış ve fonksiyonlar bu takma ad ile kullanılmıştır.
