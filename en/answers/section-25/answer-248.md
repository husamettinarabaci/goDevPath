## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: Database Applications  
#### ✅ Answer 248: Building a simple database-backed app

This solution demonstrates a basic CRUD web application in Go using SQLite as the database. The app allows users to create, read, update, and delete tasks via HTTP endpoints. It uses the `database/sql` and `net/http` packages.

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
    fmt.Println("Server running on :8080")
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
            http.Error(w, "Invalid input", http.StatusBadRequest)
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
        http.Error(w, "Method not allowed", http.StatusMethodNotAllowed)
    }
}

func taskHandler(w http.ResponseWriter, r *http.Request) {
    id := r.URL.Query().Get("id")
    switch r.Method {
    case http.MethodPut:
        var t Task
        if err := json.NewDecoder(r.Body).Decode(&t); err != nil || t.Name == "" {
            http.Error(w, "Invalid input", http.StatusBadRequest)
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
        http.Error(w, "Method not allowed", http.StatusMethodNotAllowed)
    }
}
```

> Note: Install the SQLite driver with `go get github.com/mattn/go-sqlite3`.
