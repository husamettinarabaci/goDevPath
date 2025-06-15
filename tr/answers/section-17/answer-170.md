## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya ve Dizin İşlemleri  
#### ✅ Cevap 170: Dosya izinleri ve modları

Bu program, Go'da bir dosyayı belirli izinlerle oluşturmayı, izinlerini değiştirmeyi ve ekrana yazdırmayı gösterir. `os.OpenFile` ile dosya oluşturulur, `os.Chmod` ile izinler değiştirilir, `os.Stat` ile dosya bilgisi alınarak izinler ekrana yazdırılır.

```go
package main
import (
    "fmt"
    "os"
)

func main() {
    filename := "testfile.txt"
    // Sadece sahibi için okuma/yazma (0600) ile dosya oluştur
    file, err := os.OpenFile(filename, os.O_CREATE|os.O_WRONLY, 0600)
    if err != nil {
        fmt.Println("Dosya oluşturulurken hata:", err)
        return
    }
    file.Close()

    info, err := os.Stat(filename)
    if err != nil {
        fmt.Println("Dosya bilgisi alınırken hata:", err)
        return
    }
    fmt.Printf("Değiştirilmeden önce izinler: %v\n", info.Mode().Perm())

    // İzinleri herkes için okuma/yazma (0666) olarak değiştir
    err = os.Chmod(filename, 0666)
    if err != nil {
        fmt.Println("İzinler değiştirilirken hata:", err)
        return
    }

    info, err = os.Stat(filename)
    if err != nil {
        fmt.Println("Dosya bilgisi alınırken hata:", err)
        return
    }
    fmt.Printf("Değiştirildikten sonra izinler: %v\n", info.Mode().Perm())
}
```
