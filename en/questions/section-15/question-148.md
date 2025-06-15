## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ❓ Question 148: Range over channels

Write a Go program that demonstrates how to use a `range` loop to receive values from a channel until it is closed.

- Create a channel of type `int`.
- Launch a goroutine that sends several values into the channel and then closes it.
- In the main function, use a `range` loop to receive and print all values from the channel.

🔧 **Task:** Use the `range` keyword to iterate over a channel and process all values until the channel is closed.
