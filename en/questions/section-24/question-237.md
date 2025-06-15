## 📘 Section: Common Patterns and Idioms  
### 🔹 Category: Resource cleanup with `defer`  
#### ❓ Question 237: Resource cleanup with `defer`

Write a Go program that demonstrates how to use the `defer` statement to ensure resources are properly cleaned up after use.

- Open a file for reading or writing.
- Use `defer` to close the file after all operations are complete.
- Show what happens if you forget to use `defer` for cleanup.

🔧 **Task:** Use the `defer` statement to guarantee that resources such as files are closed, even if an error occurs during processing.
