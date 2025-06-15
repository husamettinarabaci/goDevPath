## 📘 Section: Concurrency II  
### 🔹 Category: Mutexes and Synchronization  
#### ❓ Question 157: Using `sync.Map`

Write a Go program that demonstrates how to use `sync.Map` for concurrent access to a map.

- Create a `sync.Map` to store key-value pairs.
- Launch multiple goroutines that read from and write to the map concurrently.
- Show how to use `Store`, `Load`, and `Range` methods.
- Print the contents of the map after all operations are complete.

🔧 **Task:** Use `sync.Map` to safely share a map between multiple goroutines.
