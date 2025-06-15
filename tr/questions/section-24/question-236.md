## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar  
### 🔹 Kategori: Zaman aşımı için context kullanımı  
#### ❓ Soru 236: Zaman aşımı için context kullanımı

`context` paketini kullanarak bir fonksiyon çağrısı için zaman aşımı uygulamayı gösteren bir Go programı yazın.

- Uzun süren bir işlemi simüle eden bir fonksiyon oluşturun (örneğin, `time.Sleep` kullanarak).
- Bu işlem için `context.WithTimeout` ile bir zaman aşımı belirleyin.
- İşlem zaman aşımından önce tamamlanırsa ve zaman aşımı önce gerçekleşirse iki durumu da yönetin.

🔧 **Görev:** Bir fonksiyon çok uzun sürerse `context.WithTimeout` ile nasıl iptal edileceğini gösterin.
