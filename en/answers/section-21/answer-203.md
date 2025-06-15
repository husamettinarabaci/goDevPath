## 📘 Section: Advanced Go Features  
### 🔹 Category: Custom Marshaling and Unmarshaling  
#### ✅ Answer 203: Custom marshaling and unmarshaling

You can customize how a struct is marshaled to and unmarshaled from JSON by implementing the `MarshalJSON` and `UnmarshalJSON` methods. Here is an example:

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
        Age:   fmt.Sprintf("%d years", p.Age),
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
    fmt.Sscanf(aux.Age, "%d years", &p.Age)
    return nil
}

func main() {
    p := Person{"Alice", 30}
    b, _ := json.Marshal(p)
    fmt.Println(string(b))
    var p2 Person
    json.Unmarshal(b, &p2)
    fmt.Printf("%+v\n", p2)
}
```
