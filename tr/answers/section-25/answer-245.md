## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Ağ ve İletişim  
#### ✅ Cevap 245: TCP sunucu ve istemcisi geliştirme

Bu çözüm, Go'da basit bir TCP sunucu ve istemcisinin nasıl geliştirileceğini gösterir. Sunucu, bağlantıları dinler, istemciden gelen mesajları okur ve aynen geri gönderir. İstemci ise sunucuya bağlanır, bir mesaj gönderir ve yanıtı ekrana yazdırır. Her ikisi de `net` paketini kullanır.

**Sunucu:**
```go
package main

import (
    "bufio"
    "fmt"
    "net"
    "os"
)

func main() {
    ln, err := net.Listen("tcp", ":9000")
    if err != nil {
        fmt.Println("Hata:", err)
        return
    }
    defer ln.Close()
    fmt.Println("Sunucu :9000 portunda dinliyor")
    for {
        conn, err := ln.Accept()
        if err != nil {
            fmt.Println("Bağlantı hatası:", err)
            continue
        }
        go handleConnection(conn)
    }
}

func handleConnection(conn net.Conn) {
    defer conn.Close()
    reader := bufio.NewReader(conn)
    for {
        msg, err := reader.ReadString('\n')
        if err != nil {
            return
        }
        conn.Write([]byte("Echo: " + msg))
    }
}
```

**İstemci:**
```go
package main

import (
    "bufio"
    "fmt"
    "net"
    "os"
)

func main() {
    conn, err := net.Dial("tcp", "localhost:9000")
    if err != nil {
        fmt.Println("Hata:", err)
        return
    }
    defer conn.Close()

    fmt.Print("Mesaj girin: ")
    input := bufio.NewReader(os.Stdin)
    msg, _ := input.ReadString('\n')
    conn.Write([]byte(msg))

    response, _ := bufio.NewReader(conn).ReadString('\n')
    fmt.Println("Sunucu yanıtı:", response)
}
```
