## 📘 Bölüm: Mapler  
### 🔹 Kategori: Mapler  
#### ✅ Cevap 100: Map ile JSON kodlama/çözme

Bir map'i JSON'a kodlamak ve JSON'dan tekrar bir map'e çözmek için `encoding/json` paketini kullanabilirsiniz. Örnek:

```go
package main
import (
    "encoding/json"
    "fmt"
)

func main() {
    m := map[string]int{"a": 1, "b": 2}
    // JSON'a kodla
    jsonData, err := json.Marshal(m)
    if err != nil {
        fmt.Println("Kodlama hatası:", err)
        return
    }
    fmt.Println("JSON:", string(jsonData))

    // JSON'dan tekrar map'e çöz
    var m2 map[string]int
    err = json.Unmarshal(jsonData, &m2)
    if err != nil {
        fmt.Println("Çözme hatası:", err)
        return
    }
    fmt.Println("Çözülen map:", m2)
}
```
