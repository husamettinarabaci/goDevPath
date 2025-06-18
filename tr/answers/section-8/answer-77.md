## 📘 Bölüm: Structlar  
### 🔹 Kategori: Structlara Method Tanımlama  
#### ✅ Cevap 77: Structlara method tanımlama

Go'da struct'lara method tanımlayarak veri tiplerine davranış ekleyebilirsiniz. Bu, fonksiyonları belirli veri tipleriyle ilişkilendirmenizi sağlar.

```go
package main
import "fmt"

type Rectangle struct {
    width, height float64
}

func (r Rectangle) Area() float64 {
    return r.width * r.height
}

func main() {
    dikdortgen := Rectangle{width: 5, height: 3}
    fmt.Println("Alan:", dikdortgen.Area())
}
```
