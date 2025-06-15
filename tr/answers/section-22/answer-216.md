## 📘 Bölüm: Go Modülleri ve Bağımlılık Yönetimi  
### 🔹 Kategori: go.mod ve Bağımlılık Yönetimi  
#### ✅ Cevap 216: go.mod dosyasında modül değiştirme

`go.mod` dosyasındaki `replace` yönergesi, bir modül bağımlılığını yerel bir yol ile geçici olarak değiştirmeye olanak tanır. Bu, özellikle yerel geliştirme veya bir modülde değişiklikleri test etmek için kullanışlıdır.

Örneğin, ana modülünüz `example.com/mylib` bağımlılığına sahip olsun. `mylib`'in yerel bir sürümünü oluşturup `replace` ile ona yönlendirebilirsiniz:

```go
// main.go
package main
import (
    "fmt"
    "example.com/mylib"
)
func main() {
    fmt.Println(mylib.Hello())
}
```

`go.mod` dosyanızda:

```
module example.com/myapp

require example.com/mylib v0.0.0

replace example.com/mylib => ../mylib
```

Ve `../mylib/hello.go` dosyasında:

```go
package mylib
func Hello() string {
    return "Yerel mylib'den merhaba!"
}
```

Artık ana programınızı çalıştırdığınızda, uzak depodan almak yerine yerel `mylib` sürümü kullanılacaktır.
