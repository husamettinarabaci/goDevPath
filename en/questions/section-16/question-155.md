## 📘 Section: Concurrency II  
### 🔹 Category: Mutexes and Synchronization  
#### ❓ Question 155: Using `sync.Once`

Write a Go program that demonstrates how to use `sync.Once` to ensure a function is executed only once, even when called from multiple goroutines.

- Create a function that prints a message or initializes a resource.
- Launch several goroutines that attempt to call this function.
- Use `sync.Once` to guarantee the function runs only once.
- Print output to show that the function is executed a single time.

🔧 **Task:** Use `sync.Once` to ensure a function is executed only once, regardless of how many goroutines invoke it.
