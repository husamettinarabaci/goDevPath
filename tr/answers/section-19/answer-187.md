## 📘 Bölüm: Standart Kütüphane Temelleri
### 🔹 Kategori: io ve io/ioutil Paketleri
#### ✅ Cevap 187: `io` ve `io/ioutil` paketlerini kullanma

`io` ve `io/ioutil` paketleri, dosya işlemleri için pratik fonksiyonlar sunar. Go 1.16+ sürümünde `os.ReadFile` ve `os.WriteFile` tercih edilir, ancak `ioutil.ReadFile` ve `ioutil.WriteFile` hâlâ yaygın olarak kullanılır.

```go
package main
import (
    "fmt"
    "io/ioutil"
)

func main() {
    // input.txt dosyasının tüm içeriğini oku
    veri, err := ioutil.ReadFile("input.txt")
    if err != nil {
        fmt.Println("Dosya okuma hatası:", err)
    } else {
        fmt.Println("Dosya içeriği:", string(veri))
    }

    // output.txt dosyasına yaz
    err = ioutil.WriteFile("output.txt", []byte("Hello, Go!"), 0644)
    if err != nil {
        fmt.Println("Dosya yazma hatası:", err)
    } else {
        fmt.Println("output.txt dosyasına başarıyla yazıldı")
    }
}
```
