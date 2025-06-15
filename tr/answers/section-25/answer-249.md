## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Mikroservisler  
#### ✅ Cevap 249: Go ile mikroservis geliştirme

Bu çözüm, Go'da RESTful endpoint'lere sahip basit bir mikroservisin nasıl geliştirileceğini gösterir. Veriler bellek içinde saklanır ve kod düzenli şekilde yapılandırılmıştır. Servis `net/http` paketini kullanır.

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
    "net/http"
    "strconv"
    "sync"
)

type Item struct {
    ID   int    `json:"id"`
    Name string `json:"name"`
}

var (
    items = make(map[int]Item)
    mu    sync.RWMutex
    nextID = 1
)

func main() {
    http.HandleFunc("/items", itemsHandler)
    http.HandleFunc("/item", itemHandler)
    fmt.Println("Mikroservis :8080 portunda çalışıyor")
    log.Fatal(http.ListenAndServe(":8080", nil))
}

func itemsHandler(w http.ResponseWriter, r *http.Request) {
    switch r.Method {
    case http.MethodGet:
        mu.RLock()
        var list []Item
        for _, item := range items {
            list = append(list, item)
        }
        mu.RUnlock()
        json.NewEncoder(w).Encode(list)
    case http.MethodPost:
        var it Item
        if err := json.NewDecoder(r.Body).Decode(&it); err != nil || it.Name == "" {
            http.Error(w, "Geçersiz giriş", http.StatusBadRequest)
            return
        }
        mu.Lock()
        it.ID = nextID
        nextID++
        items[it.ID] = it
        mu.Unlock()
        json.NewEncoder(w).Encode(it)
    default:
        http.Error(w, "Yöntem desteklenmiyor", http.StatusMethodNotAllowed)
    }
}

func itemHandler(w http.ResponseWriter, r *http.Request) {
    idStr := r.URL.Query().Get("id")
    id, err := strconv.Atoi(idStr)
    if err != nil {
        http.Error(w, "Geçersiz ID", http.StatusBadRequest)
        return
    }
    switch r.Method {
    case http.MethodPut:
        var it Item
        if err := json.NewDecoder(r.Body).Decode(&it); err != nil || it.Name == "" {
            http.Error(w, "Geçersiz giriş", http.StatusBadRequest)
            return
        }
        mu.Lock()
        if _, ok := items[id]; !ok {
            mu.Unlock()
            http.NotFound(w, r)
            return
        }
        it.ID = id
        items[id] = it
        mu.Unlock()
        w.WriteHeader(http.StatusOK)
    case http.MethodDelete:
        mu.Lock()
        delete(items, id)
        mu.Unlock()
        w.WriteHeader(http.StatusOK)
    default:
        http.Error(w, "Yöntem desteklenmiyor", http.StatusMethodNotAllowed)
    }
}
```
