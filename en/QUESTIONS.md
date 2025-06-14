# Go Dev Path: Questions List

Below is the complete list of 250 questions, grouped by section. Each section contains 10 questions, and numbering is continuous from 1 to 250 for global clarity and consistency.

---

## 1. Getting Started
1. Outputting to the terminal with a basic Go program
2. Adding a comment in Go
3. Difference between `var` and `const` in Go
4. Using short variable declarations (`:=`)
5. Converting number types using type conversion
6. Creating a simple Go project with `go mod init`
7. Printing multiple lines to the terminal
8. Using escape characters in strings
9. Writing a multiline comment
10. Compiling and running a Go program from the terminal

## 2. Variables, Constants, and Types
11. Defining and initializing variables
12. Declaring multiple variables at once
13. Defining constants and using `iota`
14. Using basic numeric types (int, float64, etc.)
15. Type inference in variable declarations
16. Creating and using string variables
17. Creating and using boolean variables
18. Zero values in Go
19. Type conversion between numeric types
20. Using the `rune` and `byte` types

## 3. Control Flow
21. Using `if`, `else if`, and `else`
22. Using `switch` statements
23. Using `for` loops (basic iteration)
24. Using `for` as a while loop
25. Breaking out of a loop with `break`
26. Skipping a loop iteration with `continue`
27. Using labels with `break` and `continue`
28. Using `switch` with multiple cases
29. Using `fallthrough` in switch statements
30. Using `goto` in Go

## 4. I/O Basics
31. Reading input from the terminal with `fmt.Scanln`
32. Parsing user input to a number
33. Handling input errors gracefully
34. Trimming whitespace from input
35. Reading a single character from input
36. Reading input until EOF
37. Reading input with a prompt
38. Reading and parsing a float
39. Reading input into a slice
40. Reading input from a file

## 5. Functions I
41. Declaring a simple function
42. Function with parameters and return value
43. Calling a function from `main`
44. Function returning multiple values
45. Function with named return values
46. Function with variadic parameters
47. Function that calls another function
48. Function with anonymous parameters
49. Function that returns a pointer
50. Function that takes a pointer as argument

## 6. Functions II
51. Function scope and variable lifetime
52. Nested function calls
53. Introduction to anonymous functions
54. Function that returns another function
55. Passing functions as arguments
56. Using closures in Go
57. Recursion in Go functions
58. Defer statements in functions
59. Panic and recover in functions
60. Functions as fields in structs

## 7. Pointers and Memory
61. Declaring and using pointers
62. Passing pointers to functions
63. Returning pointers from functions
64. Nil pointers and zero values
65. Pointer arithmetic (not allowed in Go)
66. Using the `new` function
67. Using the `make` function
68. Pointers to arrays and slices
69. Pointers to structs
70. Dereferencing pointers

## 8. Structs
71. Defining a struct and creating an instance
72. Accessing struct fields
73. Struct with multiple field types
74. Struct embedding (composition)
75. Anonymous structs
76. Structs with pointer fields
77. Structs with methods
78. Structs and zero values
79. Comparing structs
80. Structs and JSON encoding/decoding

## 9. Arrays and Slices
81. Declaring and initializing arrays
82. Accessing and modifying array elements
83. Iterating over arrays with `for`
84. Slicing arrays to create slices
85. Declaring and initializing slices
86. Appending to a slice
87. Copying slices
88. Slices and underlying arrays
89. Multidimensional arrays and slices
90. Using the `len` and `cap` functions

## 10. Maps
91. Declaring and initializing maps
92. Adding and removing map entries
93. Accessing map values safely
94. Iterating over a map
95. Checking for key existence
96. Maps with struct values
97. Maps with slice values
98. Deleting map entries
99. Maps and zero values
100. Maps and JSON encoding/decoding

## 11. Methods and Interfaces I
101. Defining methods on structs
102. Pointer vs value receivers
103. Method chaining
104. Method with multiple receivers (not allowed in Go)
105. Defining a simple interface
106. Implementing an interface
107. Using interface values
108. Type assertions with interfaces
109. Type switches with interfaces
110. Nil interfaces and zero values

## 12. Methods and Interfaces II
111. Embedding interfaces
112. Empty interface (`interface{}`) usage
113. Interfaces and slices
114. Interfaces and maps
115. Interfaces and JSON encoding/decoding
116. Custom error types with interfaces
117. Interface composition
118. Comparing interface values
119. Interfaces and reflection
120. Interfaces and dynamic types

## 13. Packages and Imports
121. Creating and using packages
122. Importing standard library packages
123. Importing third-party packages
124. Using package-level variables
125. Using package-level functions
126. Package initialization with `init`
127. Exported vs unexported identifiers
128. Aliasing imports
129. Documentation with GoDoc
130. Organizing code with packages

## 14. Error Handling
131. Returning errors from functions
132. Using the `error` type
133. Creating custom error types
134. Using `errors.New` and `fmt.Errorf`
135. Wrapping errors
136. Handling errors with `panic` and `recover`
137. Ignoring errors (blank identifier)
138. Error handling best practices
139. Error handling in main
140. Error handling in libraries

## 15. Concurrency I
141. Introduction to goroutines
142. Launching a goroutine
143. Synchronizing with `WaitGroup`
144. Using channels for communication
145. Sending and receiving on channels
146. Buffered vs unbuffered channels
147. Closing channels
148. Range over channels
149. Select statement basics
150. Timeout with `select` and `time.After`

## 16. Concurrency II
151. Channel directions (send-only, receive-only)
152. Channel of channels
153. Using `sync.Mutex` for mutual exclusion
154. Using `sync.RWMutex`
155. Using `sync.Once`
156. Using `sync.Cond`
157. Using `sync.Map`
158. Deadlocks and race conditions
159. Detecting race conditions with `-race`
160. Best practices for concurrency

## 17. File and Directory Operations
161. Reading a file
162. Writing to a file
163. Appending to a file
164. Reading a file line by line
165. Reading and writing JSON files
166. Working with CSV files
167. Creating and deleting files
168. Creating and deleting directories
169. Walking a directory tree
170. File permissions and modes

## 18. Testing and Benchmarking
171. Writing a basic test with `testing` package
172. Table-driven tests
173. Testing error conditions
174. Using test coverage tools
175. Writing benchmarks
176. Using `go test` flags
177. Mocking in tests
178. Testing concurrent code
179. Organizing test files
180. Best practices for testing

## 19. Standard Library Essentials
181. Using the `fmt` package
182. Using the `strings` package
183. Using the `strconv` package
184. Using the `math` package
185. Using the `time` package
186. Using the `os` package
187. Using the `io` and `io/ioutil` packages
188. Using the `bufio` package
189. Using the `sort` package
190. Using the `flag` package

## 20. Networking and HTTP
191. Making HTTP GET requests
192. Making HTTP POST requests
193. Parsing JSON from HTTP responses
194. Creating a simple HTTP server
195. Handling routes in HTTP server
196. Serving static files
197. Using URL parameters
198. Handling forms in HTTP
199. Using WebSockets in Go
200. Error handling in HTTP servers

## 21. Advanced Go Features
201. Using reflection with `reflect` package
202. Using `unsafe` package
203. Custom marshaling and unmarshaling
204. Using build tags
205. Embedding files with `embed` package
206. Using generics (Go 1.18+)
207. Writing custom collection types
208. Using function types and callbacks
209. Using context for cancellation
210. Profiling Go programs

## 22. Go Modules and Dependency Management
211. Initializing a Go module
212. Adding dependencies with `go get`
213. Upgrading and downgrading dependencies
214. Using `go mod tidy`
215. Using `go mod vendor`
216. Replacing modules in `go.mod`
217. Using private modules
218. Semantic versioning in Go modules
219. Publishing a Go module
220. Best practices for dependency management

## 23. Deployment and Tooling
221. Building Go binaries
222. Cross-compiling Go programs
223. Using environment variables
224. Embedding assets in binaries
225. Using `go generate`
226. Using `go fmt` and `goimports`
227. Using `golint` and static analysis tools
228. Using `go run` and `go install`
229. Using Docker with Go
230. Continuous integration for Go projects

## 24. Common Patterns and Idioms
231. Error handling idioms
232. Functional options pattern
233. Singleton pattern in Go
234. Factory pattern in Go
235. Dependency injection basics
236. Using context for timeouts
237. Resource cleanup with `defer`
238. Working with configuration files
239. Logging best practices
240. Writing idiomatic Go code

## 25. Capstone and Real-World Scenarios
241. Building a CLI tool in Go
242. Building a REST API in Go
243. Building a concurrent web scraper
244. Building a file watcher utility
245. Building a TCP server and client
246. Building a chat application
247. Building a URL shortener
248. Building a simple database-backed app
249. Building a microservice in Go
250. Building and deploying a Go web application

---

All content is in English for global accessibility. Each section contains 10 questions, for a total of 250, numbered consecutively.


