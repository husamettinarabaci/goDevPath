# Q&A File Format Guide

This document describes the required format for English question and answer files in this repository.

---

## Question File (`tr/questions/section-YY/question-XX.md`)

- **Section, Category, and Question Title**:  
  ```
  ## 📘 Section: <Section Name>  
  ### 🔹 Category: <Category Name>  
  #### ❓ Question XX: <Short Title>
  ```
- **Task Description**:  
  - Briefly describe what the user should do.
  - Use a bulleted list for step-by-step requirements.
  - Optionally, add a **Task** line for clarity.
- **Example**:  
  ```markdown
  ## 📘 Section: Getting Started  
  ### 🔹 Category: main Function and Printing  
  #### ❓ Question 1: Outputting to the terminal with a basic Go program

  Write a Go program that does the following:

  - Create a `main` function that prints `Hello, Go!` to the terminal.

  🔧 **Task:** Use the `fmt.Println` function to build a basic Go application that outputs text to the console.
  ```

## Answer File (`tr/answers/section-YY/answer-XX.md`)

- **Section, Category, and Answer Title**:  
  ```
  ## 📘 Section: <Section Name>  
  ### 🔹 Category: <Category Name>  
  #### ✅ Answer XX: <Short Title>
  ```
- **Explanation**:  
  - Briefly explain the solution, including any relevant Go concepts.
- **Code Block**:  
  - Use triple backticks for Go code blocks:
    ```
    ```go
    // Go code here
    package main
    import "fmt"
    func main() {
        fmt.Println("Hello, Go!")
    }
    ```
    ```
- **Example**:  
  ```markdown
  ## 📘 Section: Getting Started  
  ### 🔹 Category: main Function and Printing  
  #### ✅ Answer 1: Outputting to the terminal with a basic Go program

  This is one of the simplest working programs in Go. The `main` function is the entry point, and the `fmt.Println` function prints text to the terminal.

  ```go
  package main
  import "fmt"
  func main() {
      fmt.Println("Hello, Go!")
  }
  ```
  ```

---

## General Notes

- Use Markdown headings and formatting as shown.
- Always include section, category, and question/answer number and title.
- Keep explanations concise and relevant.
- For both languages, keep the structure and style consistent across all files.
