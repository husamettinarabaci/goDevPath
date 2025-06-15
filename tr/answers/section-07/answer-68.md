## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: Dizi ve slice'lara pointer ile erişim  
#### ✅ Cevap 68: Dizi ve slice'lara pointer ile erişim

Go'da dizilere pointer oluşturabilir ve slice'lar ile dizinin altındaki verilere referansla erişebilirsiniz. Burada, bir diziyi pointer ile değiştiriyor ve slice üzerinden yapılan değişikliğin diziye nasıl yansıdığını gösteriyoruz.

```go
package main
import "fmt"

func main() {
    arr := [3]int{1, 2, 3}
    p := &arr           // diziye pointer
    (*p)[0] = 10        // pointer ile değiştir
    fmt.Println(arr)    // çıktı: [10 2 3]

    s := arr[:]
    s[1] = 20           // slice ile değiştir
    fmt.Println(arr)    // çıktı: [10 20 3]
}
```
