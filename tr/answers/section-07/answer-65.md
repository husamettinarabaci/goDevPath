## 📘 Bölüm: Pointerlar ve Bellek  
### 🔹 Kategori: Pointer Kullanımı, new/make, Struct Pointerları  
#### ✅ Cevap 65: Pointer aritmetiği (Go'da izin verilmez)

Go'da, C veya C++'da olduğu gibi pointer aritmetiğine (pointer'a sayı ekleme/çıkarma) izin verilmez. Bu kısıtlama, bellek güvenliğini artırır ve geçersiz bellek erişimi gibi hataları önler.

```go
package main
func main() {
    var x int
    p := &x
    // Aşağıdaki satır derlenmez:
    // p = p + 1
}
```

Pointer aritmetiği yapmaya çalışırsanız derleme zamanı hatası alırsınız:

```
geçersiz işlem: p + 1 (uyumsuz tipler *int ve int)
```

Go, bu kuralı bellek manipülasyonunu güvenli ve basit tutmak için uygular.
