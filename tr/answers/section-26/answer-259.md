## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Struct ve JSON  
#### ✅ Cevap 259: Structları JSON ile kullanma

Go'nun `encoding/json` paketi struct'ları JSON'a çevirebilir. Burada bir `Product` struct'ı JSON'a çevrilip string olarak yazdırılır.

```go
package main
import (
    "encoding/json"
    "fmt"
)

type Product struct {
    ID   int    `json:"id"`
    Name string `json:"name"`
}

func main() {
    p := Product{ID: 101, Name: "Kitap"}
    data, _ := json.Marshal(p)
    fmt.Println(string(data))
}
```
