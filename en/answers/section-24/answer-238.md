## 📘 Section: Common Patterns and Idioms  
### 🔹 Category: Working with configuration files  
#### ✅ Answer 238: Working with configuration files

To work with configuration files in Go, you typically define a struct that matches the file's structure, read the file, and unmarshal its contents. Here is an example using JSON:

```go
package main

import (
    "encoding/json"
    "fmt"
    "os"
)

type Config struct {
    Port int    `json:"port"`
    Debug bool  `json:"debug"`
    Name string `json:"name"`
}

func main() {
    file, err := os.Open("config.json")
    if err != nil {
        fmt.Println("Error opening config file:", err)
        return
    }
    defer file.Close()

    var cfg Config
    decoder := json.NewDecoder(file)
    if err := decoder.Decode(&cfg); err != nil {
        fmt.Println("Error decoding config:", err)
        return
    }

    fmt.Printf("Config loaded: %+v\n", cfg)
}
```

A sample `config.json` file:

```json
{
  "port": 8080,
  "debug": true,
  "name": "MyApp"
}
```

For YAML, you can use a third-party package like `gopkg.in/yaml.v2` and follow a similar approach.
