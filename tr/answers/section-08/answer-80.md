## 📘 Bölüm: Structlar  
### 🔹 Kategori: Struct ile JSON Kodlama/Çözme  
#### ✅ Cevap 80: Struct ile JSON kodlama/çözme

Go'nun `encoding/json` paketi ile struct'lar kolayca JSON'a kodlanabilir (marshal) ve JSON'dan struct'a çözülebilir (unmarshal).

```go
package main
import (
    "encoding/json"
    "fmt"
)

type Product struct {
    Name  string  `json:"name"`
    Price float64 `json:"price"`
}

func main() {
    p := Product{Name: "Laptop", Price: 1299.99}
    // JSON'a kodla
    data, err := json.Marshal(p)
    if err != nil {
        fmt.Println("Kodlama hatası:", err)
        return
    }
    fmt.Println(string(data))

    // JSON'dan çöz
    var cozulmus Product
    err = json.Unmarshal(data, &cozulmus)
    if err != nil {
        fmt.Println("Çözme hatası:", err)
        return
    }
    fmt.Printf("Çözülen: %+v\n", cozulmus)
}
```
