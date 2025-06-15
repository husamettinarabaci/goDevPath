## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar
### 🔹 Kategori: Fonksiyonel seçenekler kalıbı
#### ✅ Cevap 232: Fonksiyonel seçenekler kalıbı

Fonksiyonel seçenekler kalıbı, struct veya fonksiyonları esnek ve okunabilir şekilde yapılandırmak için opsiyon fonksiyonlarının argüman olarak geçirilmesini sağlar. Bu, uzun parametre listelerini önler ve kodun bakımını kolaylaştırır.

```go
package main
import "fmt"

type Sunucu struct {
    Host string
    Port int
}

type Secenek func(*Sunucu)

func HostIle(host string) Secenek {
    return func(s *Sunucu) {
        s.Host = host
    }
}

func PortIle(port int) Secenek {
    return func(s *Sunucu) {
        s.Port = port
    }
}

func YeniSunucu(secenekler ...Secenek) *Sunucu {
    s := &Sunucu{Host: "localhost", Port: 8080}
    for _, sec := range secenekler {
        sec(s)
    }
    return s
}

func main() {
    sunucu := YeniSunucu(HostIle("ornek.com"), PortIle(9090))
    fmt.Printf("Sunucu: %+v\n", sunucu)
}
```

Bu kalıp, kurucu imzasını değiştirmeden yeni seçenekler eklemeyi kolaylaştırır.
