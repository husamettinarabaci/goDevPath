## 📘 Section: Concurrency II  
### 🔹 Category: Channel Directions and Synchronization  
#### ❓ Question 151: Channel directions (send-only, receive-only)

Write a Go program that demonstrates the use of send-only and receive-only channels.

- Create a function that takes a send-only channel and sends a value.
- Create a function that takes a receive-only channel and receives a value, printing it.
- In the main function, create a channel, start both functions as goroutines, and show how channel direction restrictions work.

🔧 **Task:** Use channel direction types (`chan<-`, `<-chan`) to enforce send-only and receive-only behavior in Go.
