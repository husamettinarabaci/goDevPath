## 📘 Bölüm: İleri Go Özellikleri  
### 🔹 Kategori: Profiling ve Performans  
#### ❓ Soru 210: Go programlarını profil etme

Aşağıdakileri yapan bir Go programı yazın:

- CPU yoğun bir işlem (örneğin, hesaplamalı bir döngü) içeren bir fonksiyon oluşturun.
- `runtime/pprof` ve `os` paketlerini kullanarak CPU profilini başlatıp durdurun.
- CPU profilini bir dosyaya kaydedin (örneğin, `cpu.prof`).
- Profilin başladığını ve bittiğini belirten mesajlar yazdırın.

🔧 **Görev:** Performans analizi için `pprof.StartCPUProfile` ve `pprof.StopCPUProfile` fonksiyonlarını kullanarak CPU profili toplayın.
