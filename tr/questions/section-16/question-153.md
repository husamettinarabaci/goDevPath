## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ❓ Soru 153: Karşılıklı dışlama için `sync.Mutex` kullanımı

Aşağıdaki adımları izleyerek `sync.Mutex` ile paylaşılan verinin eşzamanlı erişimden nasıl korunduğunu gösteren bir Go programı yazın:

- Paylaşılan bir tamsayı değişkeni oluşturun.
- Bu değişkeni artıran birden fazla goroutine başlatın.
- Artırma işlemlerinin güvenli olması için `sync.Mutex` kullanın.
- Tüm goroutine'ler tamamlandığında son değeri ekrana yazdırın.

🔧 **Görev:** Birden fazla goroutine paylaşılan bir değişkeni güncellerken yarış durumunu önlemek için `sync.Mutex` kullanın.
