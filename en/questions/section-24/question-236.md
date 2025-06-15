## 📘 Section: Common Patterns and Idioms  
### 🔹 Category: Using context for timeouts  
#### ❓ Question 236: Using context for timeouts

Write a Go program that demonstrates how to use the `context` package to implement a timeout for a function call.

- Create a function that simulates a long-running operation (e.g., using `time.Sleep`).
- Use `context.WithTimeout` to set a timeout for this operation.
- Handle the case where the operation completes before the timeout, and the case where the timeout occurs first.

🔧 **Task:** Show how to use `context.WithTimeout` to cancel a function if it takes too long to complete.
