## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Unsafe Paketi  
#### ✅ Cevap 202: `unsafe` paketi kullanımı

Go'da `unsafe` paketi, düşük seviyeli bellek işlemlerine olanak tanır. Burada bir struct'ın boyutu alınır ve pointer tamsayıya dönüştürülür.

```go
package main
import (
    "fmt"
    "unsafe"
)

type Data struct {
    A int32
    B float64
}

func main() {
    d := Data{42, 3.14}
    fmt.Println("Data struct'ının boyutu:", unsafe.Sizeof(d))
    ptr := &d
    uptr := uintptr(unsafe.Pointer(ptr))
    fmt.Printf("Pointer'ın uintptr karşılığı: %x\n", uptr)
}
```
