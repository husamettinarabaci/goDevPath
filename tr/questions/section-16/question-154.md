## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ❓ Soru 154: `sync.RWMutex` kullanımı

Birden fazla okuyucunun aynı anda, yalnızca bir yazıcının ise tek başına erişebildiği bir senaryoda `sync.RWMutex` kullanımını gösteren bir Go programı yazın.

- Paylaşılan bir tamsayı değişkeni oluşturun.
- Bu değişkeni okuyan birkaç goroutine ve artıran (yazan) birkaç goroutine başlatın.
- Eşzamanlı okumalar ve tekil yazmalar için `sync.RWMutex` kullanın.
- Tüm goroutine'ler tamamlandığında son değeri ekrana yazdırın.

🔧 **Görev:** Paylaşılan bir değişkene eşzamanlı okuma ve yazma erişimini yönetmek için `sync.RWMutex` kullanın.
