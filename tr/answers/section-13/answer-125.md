## 📘 Bölüm: Paketler ve İçe Aktarma  
### 🔹 Kategori: Paket Seviyesinde Fonksiyonlar Kullanma  
#### ✅ Cevap 125: Paket seviyesinde fonksiyonlar kullanma

Paket seviyesinde fonksiyonlar, herhangi bir tipe bağlı olmadan tanımlanır ve aynı paketten her yerden çağrılabilir. Burada, `Greet` fonksiyonu tanımlanıp `main` fonksiyonunda kullanılmıştır.

```go
package main

import "fmt"

func Greet(name string) string {
    return "Merhaba, " + name + "!"
}

func main() {
    fmt.Println(Greet("Ayşe"))
    fmt.Println(Greet("Mehmet"))
}
```

Bu programda, paket seviyesinde bir `Greet` fonksiyonu tanımlanır ve farklı isimlerle çağrılarak sonuçlar ekrana yazdırılır.
