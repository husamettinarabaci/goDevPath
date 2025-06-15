## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Context ve İptal Mekanizması  
#### ❓ Soru 209: İptal için context kullanımı

Aşağıdakileri yapan bir Go programı yazın:

- Uzun süren bir işlemi (örneğin, gecikmeli bir döngü) gerçekleştiren bir fonksiyon oluşturun.
- Bu işlemin iptal edilebilmesi için `context.Context` kullanın.
- İşlemi bir goroutine içinde başlatın ve ana fonksiyondan kısa bir süre sonra iptal edin.
- Görev başladığında, çalışırken ve iptal edildiğinde ekrana mesaj yazdırın.

🔧 **Görev:** Bir goroutine'in ömrünü kontrol etmek ve iptalini yönetmek için `context.WithCancel` kullanın.
