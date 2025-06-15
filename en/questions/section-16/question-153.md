## 📘 Section: Concurrency II  
### 🔹 Category: Mutex and Synchronization  
#### ❓ Question 153: Using `sync.Mutex` for mutual exclusion

Write a Go program that demonstrates how to use `sync.Mutex` to protect shared data from concurrent access.

- Create a shared integer variable.
- Launch multiple goroutines that increment this variable.
- Use a `sync.Mutex` to ensure that increments are performed safely.
- Print the final value after all goroutines complete.

🔧 **Task:** Use `sync.Mutex` to prevent race conditions when multiple goroutines update a shared variable.
