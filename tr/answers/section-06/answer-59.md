## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure, Özyineleme, Defer, Panic/Recover  
#### ✅ Cevap 59: Fonksiyonlarda panic ve recover kullanımı

Go'da `panic` ciddi bir hata durumunu belirtmek için kullanılır, `recover` ise panikleyen bir goroutine'i kontrol altına almak için kullanılabilir. `defer` ile birlikte `recover` çağrılarak panik durumu yakalanabilir ve programın çökmesi engellenir.

```go
package main
import "fmt"

func guvenliBolme(a, b int) {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Panikten kurtarıldı:", r)
        }
    }()
    if b == 0 {
        panic("sıfıra bölme hatası")
    }
    fmt.Println("Sonuç:", a/b)
}

func main() {
    guvenliBolme(10, 0)
    fmt.Println("Recover sonrası program çalışmaya devam ediyor.")
}
```

Bu örnekte sıfıra bölme hatası ile panic tetiklenir, ancak `recover` ile yakalanır ve program devam eder.
