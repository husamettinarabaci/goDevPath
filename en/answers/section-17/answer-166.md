## 📘 Section: File and Directory Operations  
### 🔹 Category: File and Directory Operations  
#### ✅ Answer 166: Working with CSV files

To work with CSV files in Go, use the `encoding/csv` package for writing and reading, and the `os` package for file operations. Always handle errors and close files when done.

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

    // Write CSV to file
    file, err := os.Create("products.csv")
    if err != nil {
        fmt.Println("Error creating file:", err)
        return
    }
    defer file.Close()

    writer := csv.NewWriter(file)
    defer writer.Flush()

    // Write header
    writer.Write([]string{"Name", "Price"})
    for _, p := range products {
        writer.Write([]string{p.Name, strconv.FormatFloat(p.Price, 'f', 2, 64)})
    }

    // Read CSV from file
    file, err = os.Open("products.csv")
    if err != nil {
        fmt.Println("Error opening file:", err)
        return
    }
    defer file.Close()

    reader := csv.NewReader(file)
    records, err := reader.ReadAll()
    if err != nil {
        fmt.Println("Error reading CSV:", err)
        return
    }

    var decoded []Product
    for i, rec := range records {
        if i == 0 {
            continue // skip header
        }
        price, _ := strconv.ParseFloat(rec[1], 64)
        decoded = append(decoded, Product{Name: rec[0], Price: price})
    }

    fmt.Println(decoded)
}
```
