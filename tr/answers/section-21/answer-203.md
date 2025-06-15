## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Özel Marshal/Unmarshal İşlemleri  
#### ✅ Cevap 203: Özel marshal/unmarshal işlemleri

Bir struct'ın JSON'a çevrilmesi ve tekrar struct'a döndürülmesi işlemlerini özelleştirmek için `MarshalJSON` ve `UnmarshalJSON` metodları uygulanabilir. İşte bir örnek:

```go
package main
import (
    "encoding/json"
    "fmt"
)

type Person struct {
    Name string
    Age  int
}

func (p Person) MarshalJSON() ([]byte, error) {
    type Alias Person
    return json.Marshal(&struct {
        Alias
        Age string `json:"age"`
    }{
        Alias: (Alias)(p),
        Age:   fmt.Sprintf("%d yaşında", p.Age),
    })
}

func (p *Person) UnmarshalJSON(data []byte) error {
    type Alias Person
    aux := &struct {
        Alias
        Age string `json:"age"`
    }{
        Alias: (Alias)(*p),
    }
    if err := json.Unmarshal(data, &aux); err != nil {
        return err
    }
    *p = Person(aux.Alias)
    fmt.Sscanf(aux.Age, "%d yaşında", &p.Age)
    return nil
}

func main() {
    p := Person{"Ayşe", 28}
    b, _ := json.Marshal(p)
    fmt.Println(string(b))
    var p2 Person
    json.Unmarshal(b, &p2)
    fmt.Printf("%+v\n", p2)
}
```
