## 📘 Bölüm: Değişkenler, Sabitler ve Tipler  
### 🔹 Kategori: String Değişkenler  
#### ✅ Cevap 16: String değişken oluşturma ve kullanma

Go'da string değişkenler tanımlanabilir, değer atanabilir ve stringler birleştirilebilir. Aşağıda bir örnek yer almaktadır:

```go
package main
import "fmt"
func main() {
    var selam string = "Merhaba"
    fmt.Println(selam)
    isim := "Go Geliştiricisi"
    mesaj := selam + ", " + isim + "!"
    fmt.Println(mesaj)
}
```

Bu program, string değişkenlerin tanımlanması, kullanılması ve birleştirilmesini göstermektedir.
