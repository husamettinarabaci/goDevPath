## 📘 Section: Concurrency II  
### 🔹 Category: Mutexes and Synchronization  
#### ❓ Question 156: Using `sync.Cond`

Write a Go program that demonstrates how to use `sync.Cond` for goroutine coordination.

- Create a shared resource (e.g., a slice or queue).
- Launch several goroutines that wait for a condition (e.g., resource becomes non-empty).
- Use `sync.Cond` to signal waiting goroutines when the resource is updated.
- Show how goroutines can wait and be notified to proceed.

🔧 **Task:** Use `sync.Cond` to coordinate goroutines waiting for a condition to be met.
