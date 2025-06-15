## 📘 Bölüm: Yaygın Kalıplar ve İdiomlar  
### 🔹 Kategori: `defer` ile kaynak temizliği  
#### ❓ Soru 237: `defer` ile kaynak temizliği

`defer` ifadesini kullanarak kaynakların kullanım sonrası düzgün şekilde temizlenmesini gösteren bir Go programı yazın.

- Okuma veya yazma için bir dosya açın.
- Tüm işlemler tamamlandıktan sonra dosyanın kapanmasını sağlamak için `defer` kullanın.
- Temizlik için `defer` kullanılmazsa ne olacağını gösterin.

🔧 **Görev:** Dosya gibi kaynakların, hata oluşsa bile, her durumda kapatılmasını garanti altına almak için `defer` ifadesini kullanın.
