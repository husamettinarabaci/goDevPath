## 📘 Bölüm: Dosya ve Dizin İşlemleri  
### 🔹 Kategori: Dosya ve Dizin İşlemleri  
#### ✅ Cevap 166: CSV dosyaları ile çalışma

Go'da CSV dosyaları ile çalışmak için `encoding/csv` paketi ile yazma/okuma ve dosya işlemleri için `os` paketi kullanılır. Hata kontrolü yapılmalı ve dosyalar kapatılmalıdır.

```go
package main

import (
    "encoding/csv"
    "fmt"
    "os"
    "strconv"
)

type Product struct {
    Name  string
    Price float64
}

func main() {
    products := []Product{
        {Name: "Book", Price: 12.99},
        {Name: "Pen", Price: 1.49},
    }

    // CSV'yi dosyaya yaz
    file, err := os.Create("products.csv")
    if err != nil {
        fmt.Println("Dosya oluşturulurken hata oluştu:", err)
        return
    }
    defer file.Close()

    writer := csv.NewWriter(file)
    defer writer.Flush()

    // Başlık satırı yaz
    writer.Write([]string{"Name", "Price"})
    for _, p := range products {
        writer.Write([]string{p.Name, strconv.FormatFloat(p.Price, 'f', 2, 64)})
    }

    // CSV'yi dosyadan oku
    file, err = os.Open("products.csv")
    if err != nil {
        fmt.Println("Dosya açılırken hata oluştu:", err)
        return
    }
    defer file.Close()

    reader := csv.NewReader(file)
    records, err := reader.ReadAll()
    if err != nil {
        fmt.Println("CSV okunurken hata oluştu:", err)
        return
    }

    var decoded []Product
    for i, rec := range records {
        if i == 0 {
            continue // başlığı atla
        }
        price, _ := strconv.ParseFloat(rec[1], 64)
        decoded = append(decoded, Product{Name: rec[0], Price: price})
    }

    fmt.Println(decoded)
}
```
