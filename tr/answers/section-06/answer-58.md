## 📘 Bölüm: Fonksiyonlar II  
### 🔹 Kategori: Kapsam, Closure, Özyineleme, Defer, Panic/Recover  
#### ✅ Cevap 58: Fonksiyonlarda defer kullanımı

Go'da `defer` ifadesi, çevreleyen fonksiyon döndükten sonra bir fonksiyon çağrısının çalıştırılmasını planlar. Defer edilen ifadeler son giren ilk çıkar (LIFO) sırasıyla çalışır. Bu örnekte, defer ile yazdırılan mesaj, fonksiyonun geri kalanı tamamlandıktan hemen sonra, fonksiyon gerçekten dönmeden önce çalışır.

```go
package main
import "fmt"

func deferGoster() {
    fmt.Println("Defer öncesi")
    defer fmt.Println("Bu mesaj defer ile en son çalışır!")
    fmt.Println("Defer sonrası, fakat fonksiyon bitmeden önce")
}

func main() {
    deferGoster()
}
```
