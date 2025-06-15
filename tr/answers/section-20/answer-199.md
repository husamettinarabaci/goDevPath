## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: Ağ ve HTTP  
#### ✅ Cevap 199: Go'da WebSocket kullanımı

Bu program, Go'da `github.com/gorilla/websocket` paketi ile basit bir WebSocket echo sunucusu oluşturmayı gösterir. Sunucu 8080 portunda dinler ve `/ws` endpoint'inde istemciden alınan mesajı tekrar gönderir.

```go
package main
import (
    "fmt"
    "net/http"
    "github.com/gorilla/websocket"
)

var upgrader = websocket.Upgrader{}

func wsHandler(w http.ResponseWriter, r *http.Request) {
    conn, err := upgrader.Upgrade(w, r, nil)
    if err != nil {
        fmt.Println("Yükseltme hatası:", err)
        return
    }
    defer conn.Close()
    for {
        mt, mesaj, err := conn.ReadMessage()
        if err != nil {
            fmt.Println("Okuma hatası:", err)
            break
        }
        fmt.Printf("Alındı: %s\n", mesaj)
        if err := conn.WriteMessage(mt, mesaj); err != nil {
            fmt.Println("Yazma hatası:", err)
            break
        }
    }
}

func main() {
    http.HandleFunc("/ws", wsHandler)
    fmt.Println("WebSocket sunucusu ws://localhost:8080/ws adresinde başlatıldı")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Sunucu hatası:", err)
    }
}
```

> Not: Gerekli paketi yüklemek için `go get github.com/gorilla/websocket` komutunu çalıştırmalısınız.
