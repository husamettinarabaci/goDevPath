## 📘 Section: Concurrency II  
### 🔹 Category: Channel Directions and Synchronization  
#### ❓ Question 152: Channel of channels

Write a Go program that demonstrates the use of a channel of channels.

- Create a channel whose elements are themselves channels of type `int`.
- Launch a goroutine that creates several `int` channels, sends them into the channel of channels, and sends a value on each.
- In the main function, receive each channel from the channel of channels and print the value received from each.

🔧 **Task:** Use a channel of channels to coordinate communication between multiple goroutines in Go.
