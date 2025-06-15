## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine ve Kanallar  
#### ❓ Soru 147: Kanal kapatma

Bir kanalın nasıl kapatılacağını ve alıcıların kanalın kapandığını nasıl tespit edebileceğini gösteren bir Go programı yazın.

- `int` tipinde bir kanal oluşturun.
- Bir goroutine başlatın, birkaç değer gönderip kanalı kapatsın.
- Ana fonksiyonda, kanaldan döngüyle değer alın ve kanalın kapandığını tespit edin.
- Her alınan değeri ve kanal kapandığında bir mesajı ekrana yazdırın.

🔧 **Görev:** Go'da `close` fonksiyonu ve "virgül ok" idiomunu kullanarak kapalı kanalları yönetin.
