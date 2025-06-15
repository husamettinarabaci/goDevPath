## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya ve Dizin İşlemleri  
#### ✅ Cevap 165: JSON dosyalarını okuma ve yazma

Go'da JSON dosyalarını okumak ve yazmak için `encoding/json` paketi ile marshal/unmarshal işlemleri ve dosya işlemleri için `os` paketi kullanılır. Hata kontrolü yapılmalı ve dosyalar kapatılmalıdır.

```go
package main

import (
    "encoding/json"
    "fmt"
    "os"
)

type Person struct {
    Name string `json:"name"`
    Age  int    `json:"age"`
}

func main() {
    people := []Person{
        {Name: "Alice", Age: 30},
        {Name: "Bob", Age: 25},
    }

    // JSON'ı dosyaya yaz
    file, err := os.Create("people.json")
    if err != nil {
        fmt.Println("Dosya oluşturulurken hata oluştu:", err)
        return
    }
    defer file.Close()

    encoder := json.NewEncoder(file)
    if err := encoder.Encode(people); err != nil {
        fmt.Println("JSON kodlanırken hata oluştu:", err)
        return
    }

    // JSON'ı dosyadan oku
    file, err = os.Open("people.json")
    if err != nil {
        fmt.Println("Dosya açılırken hata oluştu:", err)
        return
    }
    defer file.Close()

    var decoded []Person
    decoder := json.NewDecoder(file)
    if err := decoder.Decode(&decoded); err != nil {
        fmt.Println("JSON çözülürken hata oluştu:", err)
        return
    }

    fmt.Println(decoded)
}
```
