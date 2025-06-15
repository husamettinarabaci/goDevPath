## 📘 Section: Standard Library Essentials
### 🔹 Category: math/rand Package
#### ✅ Answer 185: Generating Random Numbers

The `math/rand` package provides functions for generating pseudo-random numbers. Seeding with a constant value makes the output reproducible.

```go
package main
import (
    "fmt"
    "math/rand"
    "time"
)

func main() {
    rand.Seed(time.Now().UnixNano()) // Use current time for different results each run
    randomInt := rand.Intn(100)      // 0 <= n < 100
    randomFloat := rand.Float64()    // 0.0 <= f < 1.0

    fmt.Println("Random integer:", randomInt)
    fmt.Println("Random float:", randomFloat)

    // Reproducible results with a fixed seed
    rand.Seed(42)
    fmt.Println("Seeded random integer:", rand.Intn(100))
}
```
