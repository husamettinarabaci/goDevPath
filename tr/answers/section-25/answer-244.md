## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Dosya Sistemi Araçları  
#### ✅ Cevap 244: Dosya izleyici yardımcı programı geliştirme

Bu çözüm, Go'da `fsnotify` paketi kullanılarak bir dosya izleyici yardımcı programının nasıl geliştirileceğini gösterir. Program, bir dizindeki dosya oluşturma, değiştirme ve silme olaylarını izler ve her olay için bir mesaj yazdırır. İzleyici, program manuel olarak durdurulana kadar çalışır.

```go
package main

import (
    "fmt"
    "log"
    "os"
    "github.com/fsnotify/fsnotify"
)

func main() {
    if len(os.Args) < 2 {
        fmt.Println("Kullanım: go run main.go <dizin>")
        return
    }
    dir := os.Args[1]
    watcher, err := fsnotify.NewWatcher()
    if err != nil {
        log.Fatal(err)
    }
    defer watcher.Close()

    err = watcher.Add(dir)
    if err != nil {
        log.Fatal(err)
    }

    fmt.Printf("Dizin izleniyor: %s\n", dir)
    for {
        select {
        case event, ok := <-watcher.Events:
            if !ok {
                return
            }
            fmt.Printf("Olay: %s %s\n", event.Op, event.Name)
        case err, ok := <-watcher.Errors:
            if !ok {
                return
            }
            fmt.Println("Hata:", err)
        }
    }
}
```

> Not: `fsnotify` paketini yüklemek için `go get github.com/fsnotify/fsnotify` komutunu kullanın.
