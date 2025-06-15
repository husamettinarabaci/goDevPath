## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Build Tag Kullanımı  
#### ✅ Cevap 204: Build tag kullanımı

Go'da build tag'ler, dosyaların belirli koşullarda (ör. işletim sistemi veya mimari) derlemeye dahil edilmesini sağlar. İşte Linux ve Windows için örnek:

`main_linux.go`:
```go
//go:build linux
// +build linux

package main

func PrintOS() {
    println("Linux üzerinde çalışıyor")
}
```

`main_windows.go`:
```go
//go:build windows
// +build windows

package main

func PrintOS() {
    println("Windows üzerinde çalışıyor")
}
```

`main.go`:
```go
package main

func main() {
    PrintOS()
}
```

Linux'ta derlediğinizde `main_linux.go` içindeki, Windows'ta ise `main_windows.go` içindeki `PrintOS` fonksiyonu kullanılır. Build tag'ler dosyanın en üstüne eklenir ve derleme sırasında dosya dahilini kontrol eder.
