## 📘 Bölüm: Diziler ve Dilimler  
### 🔹 Kategori: Dizi Temelleri  
#### ✅ Cevap 84: Dizilerden slice oluşturma

Go dilinde bir diziden slice oluşturmak için `dizi[başlangıç:bitiş]` slicing sözdizimi kullanılır. Başlangıç indeksi dahil, bitiş indeksi hariçtir.

```go
package main
import "fmt"

func main() {
    arr := [6]int{10, 20, 30, 40, 50, 60}
    slice := arr[1:4] // 2. ile 4. elemanlar: 20, 30, 40
    fmt.Println("Orijinal dizi:", arr)
    fmt.Println("Slice:", slice)
}
```

- `arr[1:4]` ifadesi, 1. indeksten (dahil) 4. indekse (hariç) kadar olan elemanlardan bir slice oluşturur, yani 20, 30, 40.
