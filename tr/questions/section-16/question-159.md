## 📘 Bölüm: Eşzamanlılık II  
### 🔹 Kategori: Deadlock ve Yarış Durumları  
#### ❓ Soru 159: `-race` ile yarış durumu tespiti

Bir yarış durumu (race condition) oluşturan bir Go programı yazın ve bunu `-race` bayrağı ile nasıl tespit edeceğinizi gösterin.

- Birden fazla goroutine'in senkronizasyon olmadan ortak bir değişkeni güncellediği bir program yazın.
- Yarış durumunu tespit etmek için programı `go run -race` komutu ile nasıl çalıştıracağınızı açıklayın.
- İsteğe bağlı olarak, mutex ile yarış durumunun nasıl düzeltileceğini de gösterin.

🔧 **Görev:** Bir yarış durumu örneği oluşturun ve Go'da `-race` bayrağı ile nasıl tespit edileceğini açıklayın.
