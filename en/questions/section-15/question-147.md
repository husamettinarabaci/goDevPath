## 📘 Section: Concurrency I  
### 🔹 Category: Goroutines and Channels  
#### ❓ Question 147: Closing channels

Write a Go program that demonstrates how to close a channel and how receivers can detect that a channel is closed.

- Create a channel of type `int`.
- Launch a goroutine that sends several values into the channel, then closes it.
- In the main function, receive values from the channel in a loop, detecting when the channel is closed.
- Print each received value and a message when the channel is closed.

🔧 **Task:** Use the `close` function and the "comma ok" idiom to handle closed channels in Go.
