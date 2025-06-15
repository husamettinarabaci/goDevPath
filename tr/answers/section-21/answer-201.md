## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Yansıma (Reflection)  
#### ✅ Cevap 201: `reflect` paketi ile yansıma kullanımı

Go'da `reflect` paketi, çalışma zamanında tip ve değer incelemesi yapmanızı sağlar. Burada bir struct tanımlanır ve yansıma ile alan adları ve tipleri ekrana yazdırılır.

```go
package main
import (
    "fmt"
    "reflect"
)

type Person struct {
    Name string
    Age  int
}

func main() {
    p := Person{"Alice", 30}
    t := reflect.TypeOf(p)
    v := reflect.ValueOf(p)
    fmt.Println("Tip:", t.Name())
    for i := 0; i < t.NumField(); i++ {
        field := t.Field(i)
        value := v.Field(i)
        fmt.Printf("Alan: %s\tTip: %s\tDeğer: %v\n", field.Name, field.Type, value)
    }
}
```
