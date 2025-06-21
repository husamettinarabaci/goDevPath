## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Struct Etiketleri ve Yansıma  
#### ✅ Cevap 256: Struct etiketleri ve yansıma kullanımı

Struct etiketleri, alanlar için ek bilgi sağlar. Burada JSON etiketleri ve yansıma ile bu etiketlere erişim gösterilmiştir.

```go
package main
import (
    "encoding/json"
    "fmt"
    "reflect"
)

type User struct {
    ID    int    `json:"id"`
    Email string `json:"email"`
}

func main() {
    u := User{ID: 1, Email: "user@example.com"}
    data, _ := json.Marshal(u)
    fmt.Println(string(data))

    t := reflect.TypeOf(u)
    for i := 0; i < t.NumField(); i++ {
        field := t.Field(i)
        fmt.Printf("Alan: %s, Etiket: %s\n", field.Name, field.Tag)
    }
}
```
