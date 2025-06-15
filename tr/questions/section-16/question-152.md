## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Kanal Yönleri ve Senkronizasyon  
#### ❓ Soru 152: Kanal kanalı (channel of channels)

Kanal kanalı (channel of channels) kullanımını gösteren bir Go programı yazın.

- Elemanları `int` kanalı olan bir kanal oluşturun.
- Bir goroutine başlatın, birkaç `int` kanalı oluşturup kanal kanalına göndersin ve her birine bir değer göndersin.
- Ana fonksiyonda, kanal kanalından her bir kanalı alıp, o kanaldan gelen değeri ekrana yazdırın.

🔧 **Görev:** Birden fazla goroutine arasında iletişimi koordine etmek için kanal kanalı kullanın.
