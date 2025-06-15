## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: Paket Seviyesinde Değişkenler Kullanma  
#### ✅ Cevap 124: Paket seviyesinde değişkenler kullanma

Paket seviyesinde değişkenler, herhangi bir fonksiyonun dışında tanımlanır ve tüm paket içinde erişilebilir. Burada, bir sayaç değişkeni örneği gösterilmiştir.

```go
package main

import "fmt"

var counter int = 0

func increment() {
    counter++
}

func main() {
    increment()
    fmt.Println(counter) // 1
    increment()
    fmt.Println(counter) // 2
    increment()
    fmt.Println(counter) // 3
}
```

Bu programda, `counter` adında bir paket seviyesinde değişken tanımlanır, bir fonksiyon ile artırılır ve her artırmadan sonra değeri ekrana yazdırılır.
