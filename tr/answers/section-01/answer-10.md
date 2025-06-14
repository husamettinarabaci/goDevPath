## 📘 Bölüm: Başlangıç  
### 🔹 Kategori: main Fonksiyonu ve Yazdırma  
#### ✅ Cevap 10: Go programını terminalden derleyip çalıştırma

Bir Go programını terminalden derleyip çalıştırmak için şu adımları izleyin:

1. `main.go` adında bir dosya oluşturun ve aşağıdaki kodu ekleyin:

```go
package main
import "fmt"
func main() {
    fmt.Println("Derlenmiş Go'dan merhaba!")
}
```

2. Terminali açın ve `main.go` dosyasının bulunduğu dizine gidin.

3. Programı derlemek için şu komutu kullanın:

```sh
go build main.go
```

Bu işlem, bulunduğunuz dizinde `main` (veya Windows'ta `main.exe`) adında bir çalıştırılabilir dosya oluşturur.

4. Derlenen programı çalıştırın:

```sh
./main
```

Ekranda şu çıktıyı görmelisiniz:

```
Derlenmiş Go'dan merhaba!
```
