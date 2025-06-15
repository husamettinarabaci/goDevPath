## 📘 Section: File and Directory Operations  
### 🔹 Category: File and Directory Operations  
#### ❓ Question 170: File permissions and modes

Write a Go program that does the following:

- Creates a new file named `testfile.txt` with read and write permissions for the owner only.
- Changes the file permissions to allow read and write for everyone.
- Prints the file's permissions before and after the change.
- Handles any errors that may occur during file creation or permission changes.

🔧 **Task:** Use the `os.OpenFile`, `os.Chmod`, and `os.Stat` functions to manage file permissions and display them.
