## 📘 Section: Concurrency II  
### 🔹 Category: Best Practices for Concurrency  
#### ✅ Answer 160: Best practices for concurrency

Here are some best practices for writing safe and efficient concurrent Go programs:

- **Minimize shared state:** Prefer message passing (channels) over shared memory.
- **Use channels for communication:** Use channels to synchronize and communicate between goroutines.
- **Avoid goroutine leaks:** Always ensure goroutines can exit (e.g., by closing channels or using context).
- **Protect shared data:** Use `sync.Mutex`, `sync.RWMutex`, or atomic operations for shared variables.
- **Detect race conditions:** Use the `-race` flag to find data races during development.
- **Limit goroutine count:** Avoid spawning excessive goroutines; use worker pools if needed.
- **Handle panics:** Use `recover` in goroutines if necessary to prevent crashes.
- **Avoid deadlocks:** Carefully design channel and lock usage to prevent circular waits.
- **Use context for cancellation:** Use `context.Context` to manage goroutine lifecycles.

**Example: Using a mutex to protect shared data**

```go
var mu sync.Mutex
var x int
mu.Lock()
x++
mu.Unlock()
```

**Example: Using channels for communication**

```go
ch := make(chan int)
go func() { ch <- 42 }()
value := <-ch
```
