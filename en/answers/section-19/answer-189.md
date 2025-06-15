## 📘 Section: Standard Library Essentials
### 🔹 Category: sort Package
#### ✅ Answer 189: Using the `sort` package

The `sort` package provides functions for sorting slices of built-in types and custom types. `sort.Ints` and `sort.Strings` are used for basic types, while `sort.Slice` allows custom sorting logic.

```go
package main
import (
    "fmt"
    "sort"
)

type Person struct {
    Name string
    Age  int
}

func main() {
    // Sort integers
    nums := []int{5, 2, 9, 1, 7}
    sort.Ints(nums)
    fmt.Println("Sorted integers:", nums)

    // Sort strings
    words := []string{"banana", "apple", "cherry"}
    sort.Strings(words)
    fmt.Println("Sorted strings:", words)

    // Sort slice of structs by Age
    people := []Person{
        {Name: "Alice", Age: 30},
        {Name: "Bob", Age: 25},
        {Name: "Charlie", Age: 35},
    }
    sort.Slice(people, func(i, j int) bool {
        return people[i].Age < people[j].Age
    })
    fmt.Println("People sorted by age:", people)
}
```
