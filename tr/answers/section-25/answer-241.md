## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Go ile CLI aracı geliştirme  
#### ✅ Cevap 241: Go ile CLI aracı geliştirme

Go'da basit bir CLI aracı, `flag` paketi veya doğrudan `os.Args` kullanılarak oluşturulabilir. Aşağıda, komut satırından verilen mesajı ekrana basan bir örnek verilmiştir:

```go
package main

import (
    "flag"
    "fmt"
    "os"
)

func main() {
    mesaj := flag.String("mesaj", "", "Ekrana basılacak mesaj")
    flag.Parse()

    if *mesaj == "" {
        fmt.Println("Kullanım: cli-araci -mesaj <mesajınız>")
        os.Exit(1)
    }

    fmt.Println("Eko:", *mesaj)
}
```

Bu program, `flag` paketini kullanarak `-mesaj` argümanını ayrıştırır. Mesaj verilmezse kullanım bilgisini ekrana yazar. Bu, Go ile CLI araçları geliştirmenin temel bir örneğidir.
