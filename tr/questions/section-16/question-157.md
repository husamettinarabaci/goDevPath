## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Mutex ve Senkronizasyon  
#### ❓ Soru 157: `sync.Map` kullanımı

Eşzamanlı erişim için `sync.Map` kullanımını gösteren bir Go programı yazın.

- Anahtar-değer çiftlerini saklamak için bir `sync.Map` oluşturun.
- Haritaya eşzamanlı olarak okuma ve yazma yapan birden fazla goroutine başlatın.
- `Store`, `Load` ve `Range` metodlarının nasıl kullanıldığını gösterin.
- Tüm işlemler tamamlandığında haritanın içeriğini ekrana yazdırın.

🔧 **Görev:** Birden fazla goroutine arasında haritayı güvenli şekilde paylaşmak için `sync.Map` kullanın.
