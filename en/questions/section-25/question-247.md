## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: Web Utilities  
#### ❓ Question 247: Building a URL shortener

Write a Go program to implement a simple URL shortener service.

- Accept long URLs from users (via HTTP POST or command line input).
- Generate a short, unique code for each URL and store the mapping in memory (map or similar structure).
- Provide a way to redirect users from the short URL to the original long URL (HTTP GET handler).
- Use Go's `net/http` package for the web server.
- Ensure proper error handling and input validation.

🔧 **Task:** Build a basic URL shortener web service in Go that maps short codes to long URLs and handles redirection.
