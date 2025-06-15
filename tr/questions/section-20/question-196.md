## 📘 Bölüm: Ağ ve HTTP  
### 🔹 Kategori: Ağ ve HTTP  
#### ❓ Soru 196: Statik dosya sunma

Aşağıdakileri yapan bir Go programı yazın:

- 8080 portunda bir HTTP sunucusu başlatın.
- `static` adlı bir dizinden statik dosyaları sunun.
- `/static/dosyaadi` isteklerinde ilgili dosyayı `static` dizininden sunun.
- Sunucu başladığında terminale bir mesaj yazdırın.

🔧 **Görev:** `net/http` paketi ve `http.FileServer` kullanarak bir dizinden statik dosya sunun.
