## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: Ağ ve HTTP  
#### ✅ Cevap 198: HTTP'de form işleme

Bu program, Go'da `net/http` paketi ile bir HTML formu sunmayı ve form gönderimlerini işlemeyi gösterir. Sunucu 8080 portunda dinler, `/` yolunda form sunar ve `/submit` yolunda gönderilen veriyi ekrana yazdırır.

```go
package main
import (
    "fmt"
    "net/http"
)

func formHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprint(w, `<form action="/submit" method="post">
        İsim: <input type="text" name="name">
        <input type="submit" value="Gönder">
    </form>`)
}

func submitHandler(w http.ResponseWriter, r *http.Request) {
    if err := r.ParseForm(); err != nil {
        fmt.Fprintln(w, "ParseForm() hatası:", err)
        return
    }
    name := r.FormValue("name")
    fmt.Fprintf(w, "Merhaba, %s!", name)
}

func main() {
    http.HandleFunc("/", formHandler)
    http.HandleFunc("/submit", submitHandler)
    fmt.Println("Sunucu http://localhost:8080 adresinde başlatıldı")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Println("Sunucu hatası:", err)
    }
}
```
