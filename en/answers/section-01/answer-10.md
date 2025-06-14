## 📘 Section: Getting Started  
### 🔹 Category: main Function and Printing  
#### ✅ Answer 10: Compiling and running a Go program from the terminal

To compile and run a Go program from the terminal, follow these steps:

1. Create a file named `main.go` with the following content:

```go
package main
import "fmt"
func main() {
    fmt.Println("Hello from compiled Go!")
}
```

2. Open your terminal and navigate to the directory containing `main.go`.

3. Compile the program using:

```sh
go build main.go
```

This will produce an executable named `main` (or `main.exe` on Windows).

4. Run the compiled program:

```sh
./main
```

You should see the output:

```
Hello from compiled Go!
```
