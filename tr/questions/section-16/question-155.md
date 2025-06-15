## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ❓ Soru 155: `sync.Once` kullanımı

Bir fonksiyonun, birden fazla goroutine tarafından çağrılsa bile yalnızca bir kez çalıştırılmasını sağlayan `sync.Once` kullanımını gösteren bir Go programı yazın.

- Bir mesaj yazdıran veya bir kaynağı başlatan bir fonksiyon oluşturun.
- Bu fonksiyonu çağırmaya çalışan birkaç goroutine başlatın.
- Fonksiyonun yalnızca bir kez çalıştırılması için `sync.Once` kullanın.
- Fonksiyonun gerçekten sadece bir kez çalıştığını göstermek için çıktı alın.

🔧 **Görev:** Kaç goroutine çağırırsa çağırsın, bir fonksiyonun yalnızca bir kez çalışmasını sağlamak için `sync.Once` kullanın.
