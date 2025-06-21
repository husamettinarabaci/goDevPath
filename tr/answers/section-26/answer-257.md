## 📘 Bölüm: Structlar ve Metotlar  
### 🔹 Kategori: Fabrika Fonksiyonları  
#### ✅ Cevap 257: Structlar için fabrika fonksiyonları

Fabrika fonksiyonu, genellikle bir struct'ın yeni bir örneğini pointer olarak döndürür. Burada `NewCar`, bir `Car` struct'ı oluşturur ve pointer olarak döndürür.

```go
package main
import "fmt"

type Car struct {
    Brand string
    Year  int
}

func NewCar(brand string, year int) *Car {
    return &Car{Brand: brand, Year: year}
}

func main() {
    car := NewCar("Toyota", 2022)
    fmt.Println("Marka:", car.Brand)
    fmt.Println("Yıl:", car.Year)
}
```
