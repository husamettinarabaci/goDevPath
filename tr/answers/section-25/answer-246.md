## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Ağ ve İletişim  
#### ✅ Cevap 246: Sohbet uygulaması geliştirme

Bu çözüm, Go'da TCP tabanlı basit bir sohbet uygulamasının nasıl geliştirileceğini gösterir. Sunucu, birden fazla istemciyi kabul eder ve gelen mesajları tüm bağlı istemcilere iletir. Her istemci, mesaj gönderip alabilir. Uygulama `net` paketi, goroutine ve channel kullanır.

**Sunucu:**
```go
package main

import (
    "bufio"
    "fmt"
    "net"
    "os"
)

type client chan<- string

func broadcaster(clients map[client]bool, messages chan string, entering chan client, leaving chan client) {
    for {
        select {
        case msg := <-messages:
            for cli := range clients {
                cli <- msg
            }
        case cli := <-entering:
            clients[cli] = true
        case cli := <-leaving:
            delete(clients, cli)
            close(cli)
        }
    }
}

func handleConn(conn net.Conn, messages chan string, entering chan client, leaving chan client) {
    ch := make(chan string)
    go clientWriter(conn, ch)

    entering <- ch
    input := bufio.NewScanner(conn)
    for input.Scan() {
        messages <- input.Text()
    }
    leaving <- ch
    conn.Close()
}

func clientWriter(conn net.Conn, ch <-chan string) {
    for msg := range ch {
        fmt.Fprintln(conn, msg)
    }
}

func main() {
    listener, err := net.Listen("tcp", ":9001")
    if err != nil {
        fmt.Println("Hata:", err)
        os.Exit(1)
    }
    defer listener.Close()
    messages := make(chan string)
    entering := make(chan client)
    leaving := make(chan client)
    clients := make(map[client]bool)

    go broadcaster(clients, messages, entering, leaving)
    fmt.Println("Sohbet sunucusu :9001 portunda başlatıldı")
    for {
        conn, err := listener.Accept()
        if err != nil {
            continue
        }
        go handleConn(conn, messages, entering, leaving)
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
    conn, err := net.Dial("tcp", "localhost:9001")
    if err != nil {
        fmt.Println("Hata:", err)
        return
    }
    defer conn.Close()

    go func() {
        scanner := bufio.NewScanner(conn)
        for scanner.Scan() {
            fmt.Println(scanner.Text())
        }
    }()

    input := bufio.NewScanner(os.Stdin)
    for input.Scan() {
        fmt.Fprintln(conn, input.Text())
    }
}
```
