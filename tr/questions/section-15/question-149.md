## 📘 Bölüm: Eşzamanlılık I  
### 🔹 Kategori: Goroutine ve Kanallar  
#### ❓ Soru 149: Temel select deyimi

Birden fazla kanal ile çalışmak için `select` deyiminin temel kullanımını gösteren bir Go programı yazın.

- `int` tipinde iki kanal oluşturun.
- Her birine kısa bir gecikmeden sonra değer gönderen iki goroutine başlatın.
- Ana fonksiyonda, `select` deyimi ile hangi kanaldan değer gelirse onu alıp, hangi kanaldan geldiğini ekrana yazdırın.

🔧 **Görev:** Go'da birden fazla kanal işlemini yönetmek için `select` deyimini kullanın.
