# Go Geliştirici Yolu: Soru Listesi

Aşağıda, bölüm bölüm gruplanmış toplam 250 soru yer almaktadır. Her bölümde 10 soru bulunur ve numaralandırma, küresel netlik ve tutarlılık için 1'den 250'ye kadar kesintisizdir.

---

## 1. Başlangıç
1. Temel bir Go programı ile terminale çıktı verme
2. Go'da yorum satırı ekleme
3. Go'da `var` ve `const` arasındaki fark
4. Kısa değişken tanımlama (`:=`) kullanımı
5. Sayı tiplerini tip dönüşümü ile dönüştürme
6. `go mod init` ile basit bir Go projesi oluşturma
7. Terminale birden fazla satır yazdırma
8. Stringlerde kaçış karakterleri kullanma
9. Çok satırlı yorum yazma
10. Go programını terminalden derleyip çalıştırma

## 2. Değişkenler, Sabitler ve Tipler
11. Değişken tanımlama ve başlatma
12. Birden fazla değişkeni aynı anda tanımlama
13. Sabit tanımlama ve `iota` kullanımı
14. Temel sayısal tipleri kullanma (int, float64, vb.)
15. Değişken tanımlamada tip çıkarımı
16. String değişken oluşturma ve kullanma
17. Boolean değişken oluşturma ve kullanma
18. Go'da sıfır değerler
19. Sayısal tipler arasında dönüşüm
20. `rune` ve `byte` tiplerini kullanma

## 3. Kontrol Akışı
21. `if`, `else if` ve `else` kullanımı
22. `switch` deyimi kullanımı
23. `for` döngüsü ile temel yineleme
24. `for` ile while döngüsü gibi kullanım
25. `break` ile döngüden çıkma
26. `continue` ile döngü adımını atlama
27. `break` ve `continue` ile etiket kullanımı
28. Birden fazla durumlu `switch` kullanımı
29. `switch` deyiminde `fallthrough` kullanımı
30. Go'da `goto` kullanımı

## 4. Girdi/Çıktı Temelleri
31. Terminalden `fmt.Scanln` ile giriş okuma
32. Kullanıcı girişini sayıya çevirme
33. Giriş hatalarını düzgün şekilde ele alma
34. Girişten boşlukları temizleme
35. Tek bir karakter okuma
36. EOF'a kadar giriş okuma
37. İstemli giriş okuma
38. Ondalık sayı okuma ve ayrıştırma
39. Girişi bir slice'a okuma
40. Dosyadan giriş okuma

## 5. Fonksiyonlar I
41. Basit bir fonksiyon tanımlama
42. Parametreli ve dönüş değerli fonksiyon
43. `main` fonksiyonundan başka bir fonksiyon çağırma
44. Birden fazla değer döndüren fonksiyon
45. İsimli dönüş değerli fonksiyon
46. Değişken sayıda parametreli fonksiyon
47. Başka bir fonksiyonu çağıran fonksiyon
48. İsimsiz parametreli fonksiyon
49. Pointer döndüren fonksiyon
50. Pointer parametreli fonksiyon

## 6. Fonksiyonlar II
51. Fonksiyon kapsamı ve değişken ömrü
52. İç içe fonksiyon çağrıları
53. İsimsiz fonksiyonlara giriş
54. Fonksiyon döndüren fonksiyon
55. Fonksiyonu parametre olarak geçirme
56. Go'da closure kullanımı
57. Go fonksiyonlarında özyineleme
58. Fonksiyonlarda defer kullanımı
59. Fonksiyonlarda panic ve recover
60. Struct içinde fonksiyon alanı kullanımı

## 7. Pointerlar ve Bellek
61. Pointer tanımlama ve kullanma
62. Pointer'ı fonksiyona parametre olarak geçirme
63. Fonksiyondan pointer döndürme
64. Nil pointer ve sıfır değerler
65. Pointer aritmetiği (Go'da izin verilmez)
66. `new` fonksiyonu kullanımı
67. `make` fonksiyonu kullanımı
68. Dizi ve slice'lara pointer ile erişim
69. Struct'lara pointer ile erişim
70. Pointer'ı çözümleme (dereference)

## 8. Structlar
71. Struct tanımlama ve örnek oluşturma
72. Struct alanlarına erişim
73. Birden fazla alan tipine sahip struct
74. Struct gömme (composition)
75. İsimsiz structlar
76. Pointer alanlı structlar
77. Structlara method tanımlama
78. Structlarda sıfır değerler
79. Struct karşılaştırma
80. Struct ile JSON kodlama/çözme

## 9. Diziler ve Dilimler
81. Dizi tanımlama ve başlatma
82. Dizi elemanlarına erişim ve değiştirme
83. `for` ile dizilerde yineleme
84. Dizilerden slice oluşturma
85. Slice tanımlama ve başlatma
86. Slice'a eleman ekleme
87. Slice kopyalama
88. Slice ve altında yatan diziler
89. Çok boyutlu dizi ve slice'lar
90. `len` ve `cap` fonksiyonlarını kullanma

## 10. Mapler
91. Map tanımlama ve başlatma
92. Map'e eleman ekleme ve silme
93. Map değerlerine güvenli erişim
94. Map üzerinde yineleme
95. Anahtar varlığını kontrol etme
96. Struct değerli mapler
97. Slice değerli mapler
98. Map'ten eleman silme
99. Map ve sıfır değerler
100. Map ile JSON kodlama/çözme

## 11. Metotlar ve Arayüzler I
101. Structlara metot tanımlama
102. Pointer ve değer alıcılar
103. Metot zincirleme
104. Birden fazla alıcı ile metot (Go'da izin verilmez)
105. Basit bir arayüz tanımlama
106. Bir arayüzü uygulama
107. Arayüz değerlerini kullanma
108. Arayüzlerde tip doğrulama (type assertion)
109. Arayüzlerde tip switch kullanımı
110. Nil arayüzler ve sıfır değerler

## 12. Metotlar ve Arayüzler II
111. Arayüz gömme
112. Boş arayüz (`interface{}`) kullanımı
113. Arayüz ve slice kullanımı
114. Arayüz ve map kullanımı
115. Arayüz ile JSON kodlama/çözme
116. Arayüz ile özel hata tipleri
117. Arayüz bileşimi
118. Arayüz değerlerini karşılaştırma
119. Arayüz ve yansıma (reflection)
120. Arayüz ve dinamik tipler

## 13. Paketler ve İçe Aktarma
121. Paket oluşturma ve kullanma
122. Standart kütüphane paketlerini içe aktarma
123. Üçüncü parti paketleri içe aktarma
124. Paket seviyesinde değişkenler kullanma
125. Paket seviyesinde fonksiyonlar kullanma
126. `init` ile paket başlatma
127. Dışa açık ve kapalı tanımlayıcılar
128. İçe aktarmada takma ad kullanımı
129. GoDoc ile dokümantasyon
130. Kodun paketlerle organize edilmesi

## 14. Hata Yönetimi
131. Fonksiyonlardan hata döndürme
132. `error` tipini kullanma
133. Özel hata tipleri oluşturma
134. `errors.New` ve `fmt.Errorf` kullanımı
135. Hataları sarmalama (wrapping)
136. `panic` ve `recover` ile hata yönetimi
137. Hataları yok sayma (boş tanımlayıcı)
138. Hata yönetimi en iyi uygulamaları
139. main fonksiyonunda hata yönetimi
140. Kütüphanelerde hata yönetimi

## 15. Eşzamanlılık I
141. Goroutine'lere giriş
142. Bir goroutine başlatma
143. `WaitGroup` ile senkronizasyon
144. İletişim için kanal kullanımı
145. Kanallarda gönderme ve alma
146. Tamponlu ve tamponsuz kanallar
147. Kanal kapatma
148. Kanal üzerinde range ile yineleme
149. Temel select deyimi
150. `select` ve `time.After` ile zaman aşımı

## 16. Eşzamanlılık II
151. Kanal yönleri (sadece gönderme, sadece alma)
152. Kanal kanalı (channel of channels)
153. Karşılıklı dışlama için `sync.Mutex` kullanımı
154. `sync.RWMutex` kullanımı
155. `sync.Once` kullanımı
156. `sync.Cond` kullanımı
157. `sync.Map` kullanımı
158. Deadlock ve yarış durumları
159. `-race` ile yarış durumu tespiti
160. Eşzamanlılık için en iyi uygulamalar

## 17. Dosya ve Dizin İşlemleri
161. Dosya okuma
162. Dosyaya yazma
163. Dosyaya ekleme
164. Dosyayı satır satır okuma
165. JSON dosyalarını okuma ve yazma
166. CSV dosyaları ile çalışma
167. Dosya oluşturma ve silme
168. Dizin oluşturma ve silme
169. Dizin ağacında gezinme
170. Dosya izinleri ve modları

## 18. Test ve Kıyaslama
171. `testing` paketi ile temel test yazma
172. Tablo tabanlı testler
173. Hata durumlarını test etme
174. Test kapsamı araçlarını kullanma
175. Kıyaslama (benchmark) yazma
176. `go test` bayraklarını kullanma
177. Testlerde mock kullanımı
178. Eşzamanlı kodu test etme
179. Test dosyalarını organize etme
180. Test için en iyi uygulamalar

## 19. Standart Kütüphane Temelleri
181. `fmt` paketini kullanma
182. `strings` paketini kullanma
183. `strconv` paketini kullanma
184. `math` paketini kullanma
185. `time` paketini kullanma
186. `os` paketini kullanma
187. `io` ve `io/ioutil` paketlerini kullanma
188. `bufio` paketini kullanma
189. `sort` paketini kullanma
190. `flag` paketini kullanma

## 20. Ağ ve HTTP
191. HTTP GET isteği yapma
192. HTTP POST isteği yapma
193. HTTP yanıtından JSON ayrıştırma
194. Basit bir HTTP sunucusu oluşturma
195. HTTP sunucusunda route yönetimi
196. Statik dosya sunma
197. URL parametrelerini kullanma
198. HTTP'de form işleme
199. Go'da WebSocket kullanımı
200. HTTP sunucularında hata yönetimi

## 21. İleri Go Özellikleri
201. `reflect` paketi ile yansıma kullanımı
202. `unsafe` paketi kullanımı
203. Özel marshal/unmarshal işlemleri
204. Build tag kullanımı
205. `embed` paketi ile dosya gömme
206. Generics kullanımı (Go 1.18+)
207. Özel koleksiyon tipleri yazma
208. Fonksiyon tipleri ve callback kullanımı
209. İptal için context kullanımı
210. Go programlarını profil etme

## 22. Go Modülleri ve Bağımlılık Yönetimi
211. Go modülü başlatma
212. `go get` ile bağımlılık ekleme
213. Bağımlılıkları yükseltme ve düşürme
214. `go mod tidy` kullanımı
215. `go mod vendor` kullanımı
216. `go.mod` dosyasında modül değiştirme
217. Özel modüller kullanma
218. Go modüllerinde semantik versiyonlama
219. Go modülü yayınlama
220. Bağımlılık yönetimi için en iyi uygulamalar

## 23. Dağıtım ve Araçlar
221. Go binary derleme
222. Go programlarını çapraz derleme
223. Ortam değişkenlerini kullanma
224. Binary içine varlık gömme
225. `go generate` kullanımı
226. `go fmt` ve `goimports` kullanımı
227. `golint` ve statik analiz araçları
228. `go run` ve `go install` kullanımı
229. Go ile Docker kullanımı
230. Go projeleri için sürekli entegrasyon

## 24. Yaygın Kalıplar ve İdiomlar
231. Hata yönetimi idiomları
232. Fonksiyonel seçenekler kalıbı
233. Go'da singleton kalıbı
234. Go'da factory kalıbı
235. Bağımlılık enjeksiyonu temelleri
236. Zaman aşımı için context kullanımı
237. `defer` ile kaynak temizliği
238. Yapılandırma dosyaları ile çalışma
239. Loglama için en iyi uygulamalar
240. İdiomatik Go kodu yazma

## 25. Kapsamlı ve Gerçek Dünya Senaryoları
241. Go ile CLI aracı geliştirme
242. Go ile REST API geliştirme
243. Eşzamanlı web scraper geliştirme
244. Dosya izleyici yardımcı programı geliştirme
245. TCP sunucu ve istemcisi geliştirme
246. Sohbet uygulaması geliştirme
247. URL kısaltıcı geliştirme
248. Basit veritabanı tabanlı uygulama geliştirme
249. Go ile mikroservis geliştirme
250. Go web uygulaması geliştirme ve dağıtımı

---

Tüm içerik küresel erişilebilirlik için Türkçedir. Her bölümde 10 soru bulunur ve toplamda 250 soru, ardışık olarak numaralandırılmıştır.
