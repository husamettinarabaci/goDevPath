## 📘 Section: Advanced Go Features  
### 🔹 Category: Profiling and Performance  
#### ✅ Answer 210: Profiling Go programs

Go's `runtime/pprof` package allows you to collect profiling data for CPU, memory, and more. CPU profiling helps you analyze which parts of your program consume the most processing time. You can use `pprof.StartCPUProfile` to begin profiling and `pprof.StopCPUProfile` to end it, saving the results to a file for later analysis with tools like `go tool pprof`.

Here's an example that profiles a CPU-intensive function:

```go
package main
import (
    "fmt"
    "os"
    "runtime/pprof"
)

func cpuIntensiveTask() {
    sum := 0
    for i := 0; i < 1e7; i++ {
        sum += i % 10
    }
    fmt.Println("Sum:", sum)
}

func main() {
    f, err := os.Create("cpu.prof")
    if err != nil {
        fmt.Println("Could not create CPU profile:", err)
        return
    }
    defer f.Close()

    fmt.Println("Starting CPU profiling...")
    if err := pprof.StartCPUProfile(f); err != nil {
        fmt.Println("Could not start CPU profile:", err)
        return
    }
    cpuIntensiveTask()
    pprof.StopCPUProfile()
    fmt.Println("CPU profiling stopped. Profile saved to cpu.prof")
}
```
