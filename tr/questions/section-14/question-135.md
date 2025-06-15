## 📘 Bölüm: Hata Yönetimi  
### 🔹 Kategori: Hataları Sarmalama (Wrapping)  
#### ❓ Soru 135: Hataları sarmalama (wrapping)

Hata sarmalamayı gösteren bir Go fonksiyonu yazın.

- Hata döndüren bir fonksiyon ve onu çağırıp hatayı `%w` ile `fmt.Errorf` kullanarak sarmalayan başka bir fonksiyon tanımlayın.
- `main` fonksiyonunda, dıştaki fonksiyonu çağırın ve `errors.Is` veya `errors.Unwrap` ile orijinal hatayı kontrol edin veya çıkarın.
- Sarılmış hatayı yazdırın ve hata incelemesini gösterin.

🔧 **Görev:** Go'nun hata sarmalama özelliklerini kullanarak hata sarmalama ve inceleme işlemlerini gösterin.
