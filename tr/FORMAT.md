# Soru & Cevap Dosya Formatı Rehberi

Bu belge, bu depodaki Türkçe soru ve cevap dosyaları için gerekli formatı açıklar.

---

## Soru Dosyası (`tr/questions/section-YY/question-XX.md`)

- **Bölüm, Kategori ve Soru Başlığı**:  
  ```
  ## 📘 Bölüm: <Bölüm Adı>  
  ### 🔹 Kategori: <Kategori Adı>  
  #### ❓ Soru XX: <Kısa Başlık>
  ```
- **Görev Açıklaması**:  
  - Kullanıcının ne yapması gerektiğini kısaca açıklayın.
  - Adım adım gereksinimler için madde işaretleri kullanın.
  - İsteğe bağlı olarak, açıklık için bir **Görev** satırı ekleyin.
- **Örnek**:  
  ```markdown
  ## 📘 Bölüm: Başlangıç  
  ### 🔹 Kategori: main Fonksiyonu ve Yazdırma  
  #### ❓ Soru 1: Temel bir Go programı ile terminale çıktı verme

  Aşağıdakileri yapan bir Go programı yazın:

  - `main` fonksiyonunu oluşturun ve terminale `Hello, Go!` yazdırın.

  🔧 **Görev:** Konsola metin yazdırmak için `fmt.Println` fonksiyonunu kullanarak temel bir Go uygulaması oluşturun.
  ```

## Cevap Dosyası (`tr/answers/section-YY/answer-XX.md`)

- **Bölüm, Kategori ve Cevap Başlığı**:  
  ```
  ## 📘 Bölüm: <Bölüm Adı>  
  ### 🔹 Kategori: <Kategori Adı>  
  #### ✅ Cevap XX: <Kısa Başlık>
  ```
- **Açıklama**:  
  - Çözümü kısaca açıklayın, ilgili Go kavramlarını dahil edin.
- **Kod Bloğu**:  
  - Go kod blokları için üçlü tırnak işareti kullanın:
    ```
    ```go
    // Go kodu buraya
    package main
    import "fmt"
    func main() {
        fmt.Println("Hello, Go!")
    }
    ```
    ```
- **Örnek**:  
  ```markdown
  ## 📘 Bölüm: Başlangıç  
  ### 🔹 Kategori: main Fonksiyonu ve Yazdırma  
  #### ✅ Cevap 1: Temel bir Go programı ile terminale çıktı verme

  Bu, Go'da en basit çalışan programlardan biridir. `main` fonksiyonu giriş noktasıdır ve `fmt.Println` fonksiyonu terminale metin yazdırır.

  ```go
  package main
  import "fmt"
  func main() {
      fmt.Println("Hello, Go!")
  }
  ```
  ```

---

## Genel Notlar

- Gösterildiği gibi Markdown başlıkları ve biçimlendirmesini kullanın.
- Her zaman bölüm, kategori ve soru/cevap numarası ile başlık ekleyin.
- Açıklamaları kısa ve ilgili tutun.
- Her iki dilde de yapı ve stil tüm dosyalarda tutarlı olmalıdır.
