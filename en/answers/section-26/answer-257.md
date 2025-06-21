## 📘 Section: Structs and Methods  
### 🔹 Category: Factory Functions  
#### ✅ Answer 257: Factory functions for structs

A factory function returns a new instance of a struct, often as a pointer. Here, `NewCar` creates and returns a pointer to a `Car` struct.

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
    fmt.Println("Brand:", car.Brand)
    fmt.Println("Year:", car.Year)
}
```
