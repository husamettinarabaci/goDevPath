## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ❓ Question 150: Timeout with `select` and `time.After`

Write a Go program that demonstrates how to implement a timeout when waiting for a value from a channel using `select` and `time.After`.

- Create a channel of type `int`.
- Use a `select` statement to wait for either a value from the channel or a timeout using `time.After` (e.g., 1 second).
- Print a message if a value is received, or a timeout message if the channel does not send a value in time.

🔧 **Task:** Use `select` and `time.After` to implement a timeout for channel operations in Go.
