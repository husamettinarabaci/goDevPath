## 📘 Bölüm: Diziler ve Dilimler  
### 🔹 Kategori: Çok Boyutlu Dizi ve Slice'lar  
#### ✅ Cevap 89: Çok boyutlu dizi ve slice'lar

Go'da hem çok boyutlu diziler hem de slice'lar desteklenir. Kullanımı aşağıda gösterilmiştir:

```go
package main
import "fmt"

func main() {
    // 2D dizi (3x2)
    dizi := [3][2]int{{1, 2}, {3, 4}, {5, 6}}
    fmt.Println("2D dizi:")
    for i := 0; i < 3; i++ {
        for j := 0; j < 2; j++ {
            fmt.Print(dizi[i][j], " ")
        }
        fmt.Println()
    }
    // 2D slice
    slice := [][]int{{7, 8}, {9, 10}}
    fmt.Println("2D slice:")
    for i := range slice {
        for j := range slice[i] {
            fmt.Print(slice[i][j], " ")
        }
        fmt.Println()
    }
}
```

- Dizi `[3][2]int` olarak tanımlanıp başlatılır.
- Slice ise `[][]int` olarak tanımlanır ve başlatılır.
- İç içe döngülerle tüm elemanlar yazdırılır.
