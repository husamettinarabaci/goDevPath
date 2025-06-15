## 📘 Section: Advanced Go Features  
### 🔹 Category: Context and Cancellation  
#### ❓ Question 209: Using context for cancellation

Write a Go program that demonstrates how to use the `context` package for cancellation:

- Create a function that performs a long-running task (e.g., a loop with delays).
- Use a `context.Context` to allow cancellation of the task from the main function.
- Start the task in a goroutine and cancel it after a short delay.
- Print messages to show when the task starts, is running, and is cancelled.

🔧 **Task:** Use `context.WithCancel` to control the lifetime of a goroutine and handle cancellation properly.
