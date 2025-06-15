## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Profiling ve Performans  
#### ✅ Cevap 210: Go programlarını profil etme

Go'nun `runtime/pprof` paketi, CPU, bellek ve diğer kaynaklar için profil verisi toplamanıza olanak tanır. CPU profili, programınızın hangi bölümlerinin en fazla işlemci süresi kullandığını analiz etmenizi sağlar. `pprof.StartCPUProfile` ile profil başlatılır, `pprof.StopCPUProfile` ile sonlandırılır ve sonuçlar bir dosyaya kaydedilir. Bu dosya daha sonra `go tool pprof` gibi araçlarla analiz edilebilir.

Aşağıda, CPU yoğun bir fonksiyonun profilini alan bir örnek bulunmaktadır:

```go
package main
import (
    "fmt"
    "os"
    "runtime/pprof"
)

func cpuYogunIslem() {
    toplam := 0
    for i := 0; i < 1e7; i++ {
        toplam += i % 10
    }
    fmt.Println("Toplam:", toplam)
}

func main() {
    f, err := os.Create("cpu.prof")
    if err != nil {
        fmt.Println("CPU profili oluşturulamadı:", err)
        return
    }
    defer f.Close()

    fmt.Println("CPU profili başlatılıyor...")
    if err := pprof.StartCPUProfile(f); err != nil {
        fmt.Println("CPU profili başlatılamadı:", err)
        return
    }
    cpuYogunIslem()
    pprof.StopCPUProfile()
    fmt.Println("CPU profili durduruldu. Profil cpu.prof dosyasına kaydedildi.")
}
```
