## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine ve Kanallar  
#### ❓ Soru 150: `select` ve `time.After` ile zaman aşımı

Bir kanaldan değer beklerken `select` ve `time.After` kullanarak zaman aşımı nasıl uygulanır, bunu gösteren bir Go programı yazın.

- `int` tipinde bir kanal oluşturun.
- `select` deyimi ile kanaldan değer gelmesini veya `time.After` ile (örneğin 1 saniye) zaman aşımını bekleyin.
- Değer alınırsa ekrana yazdırın, zaman aşımı olursa zaman aşımı mesajı yazdırın.

🔧 **Görev:** Go'da kanal işlemleri için `select` ve `time.After` kullanarak zaman aşımı uygulayın.
