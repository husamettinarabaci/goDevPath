## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ❓ Soru 156: `sync.Cond` kullanımı

Goroutine'ler arası koordinasyon için `sync.Cond` kullanımını gösteren bir Go programı yazın.

- Paylaşılan bir kaynak (ör. slice veya kuyruk) oluşturun.
- Bir koşulu bekleyen birkaç goroutine başlatın (ör. kaynak boş değilse).
- Kaynak güncellendiğinde bekleyen goroutine'leri uyarmak için `sync.Cond` kullanın.
- Goroutine'lerin bekleyip, uyarı ile devam edebildiğini gösterin.

🔧 **Görev:** Bir koşulun sağlanmasını bekleyen goroutine'leri koordine etmek için `sync.Cond` kullanın.
