## 📘 Section: Networking and HTTP  
### 🔹 Category: Networking and HTTP  
#### ❓ Question 196: Serving static files

Write a Go program that does the following:

- Starts an HTTP server on port 8080.
- Serves static files from a directory named `static`.
- Requests to `/static/filename` should serve the corresponding file from the `static` directory.
- Prints a message to the terminal when the server starts.

🔧 **Task:** Use the `net/http` package and `http.FileServer` to serve static files from a directory.
