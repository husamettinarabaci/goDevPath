## 📘 Bölüm: Dağıtım ve Araçlar  
### 🔹 Kategori: Go ile Docker kullanımı  
#### ✅ Cevap 229: Go ile Docker kullanımı

Bir Go uygulamasını container haline getirmek için çok aşamalı (multi-stage) Docker build kullanılır. İşte adımlar:

1. **main.go**
```go
package main
import "fmt"
func main() {
    fmt.Println("Hello from Dockerized Go!")
}
```

2. **Dockerfile**
```Dockerfile
# Derleme aşaması
FROM golang:1.21-alpine AS builder
WORKDIR /app
COPY main.go ./
RUN go build -o app main.go

# Son imaj
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/app .
CMD ["./app"]
```

3. **Container'ı oluşturma ve çalıştırma:**
```sh
docker build -t go-docker-demo .
docker run --rm go-docker-demo
```

Bu yöntemle, son imaj küçük olur ve sadece derlenmiş binary içerir.
