## 📘 Bölüm: Kapsamlı ve Gerçek Dünya Senaryoları  
### 🔹 Kategori: Veritabanı Uygulamaları  
#### ✅ Cevap 248: Basit veritabanı tabanlı uygulama geliştirme

Bu çözüm, Go'da SQLite veritabanı kullanarak temel bir CRUD web uygulamasının nasıl geliştirileceğini gösterir. Uygulama, kullanıcıların görev eklemesini, okumasını, güncellemesini ve silmesini HTTP endpoint'leri üzerinden sağlar. `database/sql` ve `net/http` paketleri kullanılmıştır.

```go
package main

import (
    "database/sql"
    "encoding/json"
    "fmt"
    "log"
    "net/http"
    _ "github.com/mattn/go-sqlite3"
)

type Task struct {
    ID   int    `json:"id"`
    Name string `json:"name"`
}

var db *sql.DB

func main() {
    var err error
    db, err = sql.Open("sqlite3", "tasks.db")
    if err != nil {
        log.Fatal(err)
    }
    defer db.Close()
    _, err = db.Exec(`CREATE TABLE IF NOT EXISTS tasks (id INTEGER PRIMARY KEY AUTOINCREMENT, name TEXT)`)
    if err != nil {
        log.Fatal(err)
    }

    http.HandleFunc("/tasks", tasksHandler)
    http.HandleFunc("/task", taskHandler)
    fmt.Println("Sunucu :8080 portunda çalışıyor")
    log.Fatal(http.ListenAndServe(":8080", nil))
}

func tasksHandler(w http.ResponseWriter, r *http.Request) {
    switch r.Method {
    case http.MethodGet:
        rows, err := db.Query("SELECT id, name FROM tasks")
        if err != nil {
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }
        defer rows.Close()
        var tasks []Task
        for rows.Next() {
            var t Task
            rows.Scan(&t.ID, &t.Name)
            tasks = append(tasks, t)
        }
        json.NewEncoder(w).Encode(tasks)
    case http.MethodPost:
        var t Task
        if err := json.NewDecoder(r.Body).Decode(&t); err != nil || t.Name == "" {
            http.Error(w, "Geçersiz giriş", http.StatusBadRequest)
            return
        }
        res, err := db.Exec("INSERT INTO tasks (name) VALUES (?)", t.Name)
        if err != nil {
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }
        id, _ := res.LastInsertId()
        t.ID = int(id)
        json.NewEncoder(w).Encode(t)
    default:
        http.Error(w, "Yöntem desteklenmiyor", http.StatusMethodNotAllowed)
    }
}

func taskHandler(w http.ResponseWriter, r *http.Request) {
    id := r.URL.Query().Get("id")
    switch r.Method {
    case http.MethodPut:
        var t Task
        if err := json.NewDecoder(r.Body).Decode(&t); err != nil || t.Name == "" {
            http.Error(w, "Geçersiz giriş", http.StatusBadRequest)
            return
        }
        _, err := db.Exec("UPDATE tasks SET name=? WHERE id=?", t.Name, id)
        if err != nil {
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }
        w.WriteHeader(http.StatusOK)
    case http.MethodDelete:
        _, err := db.Exec("DELETE FROM tasks WHERE id=?", id)
        if err != nil {
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }
        w.WriteHeader(http.StatusOK)
    default:
        http.Error(w, "Yöntem desteklenmiyor", http.StatusMethodNotAllowed)
    }
}
```

> Not: SQLite sürücüsünü yüklemek için `go get github.com/mattn/go-sqlite3` komutunu kullanın.
