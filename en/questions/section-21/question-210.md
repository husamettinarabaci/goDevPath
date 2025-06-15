## 📘 Section: Advanced Go Features  
### 🔹 Category: Profiling and Performance  
#### ❓ Question 210: Profiling Go programs

Write a Go program that demonstrates how to profile CPU usage:

- Create a simple program with a function that performs some CPU-intensive work (e.g., a loop with calculations).
- Use the `runtime/pprof` and `os` packages to start and stop CPU profiling.
- Save the CPU profile to a file (e.g., `cpu.prof`).
- Print a message indicating when profiling starts and ends.

🔧 **Task:** Use `pprof.StartCPUProfile` and `pprof.StopCPUProfile` to collect CPU profiling data for performance analysis.
