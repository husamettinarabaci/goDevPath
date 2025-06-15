## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar  
### 🔹 Kategori: Yapılandırma dosyaları ile çalışma  
#### ✅ Cevap 238: Yapılandırma dosyaları ile çalışma

Go'da yapılandırma dosyalarıyla çalışmak için genellikle dosya yapısına uygun bir struct tanımlanır, dosya okunur ve içeriği struct'a aktarılır. Aşağıda JSON ile bir örnek verilmiştir:

```go
package main

import (
    "encoding/json"
    "fmt"
    "os"
)

type Config struct {
    Port  int    `json:"port"`
    Debug bool   `json:"debug"`
    Name  string `json:"name"`
}

func main() {
    dosya, err := os.Open("config.json")
    if err != nil {
        fmt.Println("Yapılandırma dosyası açılırken hata:", err)
        return
    }
    defer dosya.Close()

    var cfg Config
    decoder := json.NewDecoder(dosya)
    if err := decoder.Decode(&cfg); err != nil {
        fmt.Println("Yapılandırma çözülürken hata:", err)
        return
    }

    fmt.Printf("Yapılandırma yüklendi: %+v\n", cfg)
}
```

Örnek bir `config.json` dosyası:

```json
{
  "port": 8080,
  "debug": true,
  "name": "Uygulamam"
}
```

YAML için `gopkg.in/yaml.v2` gibi üçüncü parti bir paket kullanabilir ve benzer bir yol izleyebilirsiniz.
