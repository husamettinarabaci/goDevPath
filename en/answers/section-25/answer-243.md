## 📘 Section: Capstone and Real-World Scenarios  
### 🔹 Category: Building a concurrent web scraper  
#### ✅ Answer 243: Building a concurrent web scraper

A concurrent web scraper in Go can use goroutines and channels to fetch multiple URLs in parallel. Here is a simple example:

```go
package main

import (
    "fmt"
    "net/http"
)

func fetch(url string, ch chan<- string) {
    resp, err := http.Get(url)
    if err != nil {
        ch <- fmt.Sprintf("%s: error: %v", url, err)
        return
    }
    ch <- fmt.Sprintf("%s: %d", url, resp.StatusCode)
    resp.Body.Close()
}

func main() {
    urls := []string{
        "https://www.google.com",
        "https://www.golang.org",
        "https://www.github.com",
    }
    ch := make(chan string)
    for _, url := range urls {
        go fetch(url, ch)
    }
    for range urls {
        fmt.Println(<-ch)
    }
}
```

This program launches a goroutine for each URL, fetches the HTTP status code, and prints the results as they arrive via the channel.
