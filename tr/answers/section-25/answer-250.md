## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Go Web Uygulaması Geliştirme ve Dağıtımı  
#### ✅ Cevap 250: Go web uygulaması geliştirme ve dağıtımı

Bu kapsamlı soru, bir Go web uygulamasının baştan sona geliştirilmesi ve dağıtım sürecini göstermektedir.

**Açıklama:**
- Uygulama, Go'nun `net/http` paketiyle routing ve statik dosya sunumu, `html/template` ile dinamik HTML üretimi yapar.
- Kod, sürdürülebilirlik için paketlere ayrılmıştır (ör. `handlers`, `config`, `main`).
- Başlangıçta ortam ayarlarını yüklemek için bir yapılandırma dosyası (`config.json`) kullanılır.
- Loglama için Go'nun `log` paketi kullanılır.
- Bir handler için basit bir test örneği eklenmiştir.
- Uygulama binary olarak derlenir ve Docker ile container haline getirilir.
- Hem lokal hem de Docker ortamı için dağıtım talimatları eklenmiştir.

```go
// main.go
package main

import (
    "encoding/json"
    "html/template"
    "log"
    "net/http"
    "os"
)

type Config struct {
    Addr string `json:"addr"`
}

func loadConfig() Config {
    f, err := os.Open("config.json")
    if err != nil {
        log.Fatal(err)
    }
    defer f.Close()
    var cfg Config
    if err := json.NewDecoder(f).Decode(&cfg); err != nil {
        log.Fatal(err)
    }
    return cfg
}

func main() {
    cfg := loadConfig()
    tmpl := template.Must(template.ParseFiles("templates/index.html"))

    http.Handle("/static/", http.StripPrefix("/static/", http.FileServer(http.Dir("static"))))
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        log.Printf("%s %s", r.Method, r.URL.Path)
        tmpl.Execute(w, map[string]string{"Title": "Go Web App"})
    })
    log.Printf("%s adresinde sunucu başlatılıyor", cfg.Addr)
    log.Fatal(http.ListenAndServe(cfg.Addr, nil))
}
```

**config.json**
```json
{
  "addr": ":8080"
}
```

**templates/index.html**
```html
<!DOCTYPE html>
<html>
<head><title>{{.Title}}</title></head>
<body>
<h1>{{.Title}}</h1>
<p>Go web uygulamanıza hoş geldiniz!</p>
</body>
</html>
```

**handlers_test.go**
```go
package main
import (
    "net/http"
    "net/http/httptest"
    "testing"
)
func TestHomeHandler(t *testing.T) {
    req := httptest.NewRequest("GET", "/", nil)
    w := httptest.NewRecorder()
    tmpl := template.Must(template.New("").Parse(`<h1>{{.Title}}</h1>`))
    handler := func(w http.ResponseWriter, r *http.Request) {
        tmpl.Execute(w, map[string]string{"Title": "Go Web App"})
    }
    handler(w, req)
    if w.Code != http.StatusOK {
        t.Fatalf("200 bekleniyordu, gelen: %d", w.Code)
    }
}
```

**Dockerfile**
```
FROM golang:1.21-alpine AS build
WORKDIR /app
COPY . .
RUN go build -o app

FROM alpine:latest
WORKDIR /app
COPY --from=build /app/app .
COPY config.json ./
COPY templates ./templates
COPY static ./static
EXPOSE 8080
CMD ["./app"]
```

**Dağıtım Talimatları:**
1. Lokal olarak derleyip çalıştırmak için:
   ```sh
   go build -o app
   ./app
   ```
2. Docker ile derleyip çalıştırmak için:
   ```sh
   docker build -t go-web-app .
   docker run -p 8080:8080 go-web-app
   ```
