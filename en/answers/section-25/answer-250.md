## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: Building and Deploying Go Web Applications  
#### ✅ Answer 250: Building and deploying a Go web application

This capstone demonstrates the end-to-end process of building and deploying a Go web application.

**Explanation:**
- The app uses Go's `net/http` for routing and serving static files, and `html/template` for dynamic HTML rendering.
- Code is organized into packages (e.g., `handlers`, `config`, `main`).
- A configuration file (e.g., `config.json`) is loaded at startup for environment-specific settings.
- Logging is implemented using Go's `log` package.
- A simple test is provided for a handler.
- The app is built as a binary and containerized with Docker.
- Deployment instructions are included for both local and Docker environments.

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
    log.Printf("Starting server at %s", cfg.Addr)
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
<p>Welcome to your Go web app!</p>
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
        t.Fatalf("expected 200, got %d", w.Code)
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

**Deployment Instructions:**
1. Build and run locally:
   ```sh
   go build -o app
   ./app
   ```
2. Build and run with Docker:
   ```sh
   docker build -t go-web-app .
   docker run -p 8080:8080 go-web-app
   ```
