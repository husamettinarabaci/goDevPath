## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar  
### 🔹 Kategori: Zaman aşımı için context kullanımı  
#### ✅ Cevap 236: Zaman aşımı için context kullanımı

`context.WithTimeout` fonksiyonu, bir işlemin çok uzun sürmesi durumunda otomatik olarak iptal edilmesini sağlar. Bu örnekte, uzun süren bir görev bir goroutine içinde başlatılır. Görev zaman aşımından önce biterse sonucu yazdırılır. Zaman aşımı önce gerçekleşirse context iptal edilir ve zaman aşımı mesajı gösterilir.

```go
package main

import (
    "context"
    "fmt"
    "time"
)

func uzunIslem(ctx context.Context) error {
    select {
    case <-time.After(3 * time.Second):
        return nil // İşlem tamamlandı
    case <-ctx.Done():
        return ctx.Err()
    }
}

func main() {
    ctx, cancel := context.WithTimeout(context.Background(), 2*time.Second)
    defer cancel()

    err := uzunIslem(ctx)
    if err != nil {
        fmt.Println("İşlem başarısız:", err)
    } else {
        fmt.Println("İşlem başarıyla tamamlandı")
    }
}
```
