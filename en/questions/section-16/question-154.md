## 📘 Section: Concurrency II  
### 🔹 Category: Mutexes and Synchronization  
#### ❓ Question 154: Using `sync.RWMutex`

Write a Go program that demonstrates how to use `sync.RWMutex` to allow multiple readers but only one writer for shared data.

- Create a shared integer variable.
- Launch several goroutines that read the variable and several that write (increment) it.
- Use `sync.RWMutex` to allow concurrent reads but exclusive writes.
- Print the final value after all goroutines complete.

🔧 **Task:** Use `sync.RWMutex` to manage concurrent read and write access to a shared variable.
