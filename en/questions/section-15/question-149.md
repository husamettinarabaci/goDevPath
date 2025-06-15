## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ❓ Question 149: Select statement basics

Write a Go program that demonstrates the basics of the `select` statement for working with multiple channels.

- Create two channels of type `int`.
- Launch two goroutines, each sending a value into one of the channels after a short delay.
- In the main function, use a `select` statement to receive from either channel and print which channel the value came from.

🔧 **Task:** Use the `select` statement to handle multiple channel operations in Go.
