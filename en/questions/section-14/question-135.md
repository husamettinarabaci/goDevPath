## 📘 Section: Error Handling  
### 🔹 Category: Wrapping Errors  
#### ❓ Question 135: Wrapping errors

Write a Go function that demonstrates error wrapping.

- Define a function that returns an error, and another function that calls it and wraps the error using `fmt.Errorf` with `%w`.
- In `main`, call the outer function and use `errors.Is` or `errors.Unwrap` to check or extract the original error.
- Print the wrapped error and demonstrate error inspection.

🔧 **Task:** Show how to wrap and inspect errors using Go's error wrapping features.
