# Vancrone Ana Sayfa Rehberi ve Özellik Özeti

> Bu belge; Vancrone'un ana ekranını, garanti takibini, araçlarını ve güvenlik özelliklerini anlatan resmî kullanım kılavuzudur. Son güncelleme: 15 Ekim 2026.

---

## 1. Genel Bakış ve Çevrimdışı (Offline-First) Mimari

Vancrone; satın aldığınız ürünlerin garanti sürelerini, iade sürelerini, faturalarını ve mülkiyet kanıtlarını takip eden bağımsız bir dijital envanter ve kasa uygulamasıdır. Mevcut sürüm ücretsizdir: tüm özellikler sınırsız açıktır, reklam ve uygulama içi satın alma yoktur.

- **Çevrimdışı ve Yerel Depolama:** Kayıtlarınız, faturalarınız ve fotoğraflarınız cihazınızdan çıkmaz; Vancrone sunucusu, kullanıcı hesabı veya bulut veritabanı yoktur. Google Firebase Crashlytics'e yalnızca içeriğinizi barındırmayan çökme raporları gönderilir; bunu **Ayarlar > Hakkında > Çökme Raporları** üzerinden kapatabilirsiniz (bkz. Gizlilik Politikası).
- **Şifreli Yerel Kasa:** Kayıtlarınız AES-256 ile şifrelenmiş bir veritabanında (SQLCipher) saklanır. Fatura fotoğrafları, belgeler ve videolar cihazınızda uygulamanın özel depolama alanında tutulur.
- **Kullanıcı Sorumluluğu ve Yedekleme:** Verileriniz yalnızca cihazınızda bulunduğundan düzenli yedek almak sizin sorumluluğunuzdadır. Cihazınız kaybolur, sıfırlanır veya bozulursa geliştirici verilerinizi kurtaramaz. **Ayarlar > Veri Yönetimi > Yedekle (Dışa Aktar)** ile şifreli `.vcb` dosyasını dilerseniz parolayla koruyarak seçtiğiniz yere kaydedin; aynı veya yeni telefonda **Geri Yükle (İçe Aktar)** ile geri getirin.

---

## 2. Üst Uygulama Çubuğu

- **Takvim:** Takvim simgesi, garanti bitiş tarihlerini gösteren aylık bir takvim açar. Bir güne dokunarak o gün süresi dolan ürünleri görebilirsiniz.
- **Kullanım Rehberi & S.S.S.:** Soru işareti simgesi; yedekleme, gizlilik, tarama, raporlar ve diğer konulardaki uygulama içi cevapları açar.
- **Seçim Modu:** Herhangi bir garanti kartına uzun basarak seçime başlayın. Üst çubuk seçilen ürün sayısını gösterir; tümünü tek seferde çöp kutusuna taşıyabilir veya seçimi iptal edebilirsiniz.

---

## 3. Güvence Altındaki Varlıklar Kartı

Listenin en üstündeki kart, kayıtlı ürünlerinizin toplam değerini gösterir.

- **Para Birimine Göre Toplamlar:** Tutarlar her para birimi için ayrı toplanır (örneğin ₺, $, €, ¥); para birimleri birbirine çevrilmez.
- **Döküm:** Karta dokunarak para birimi bazındaki dökümü açıp kapatabilirsiniz.

---

## 4. Arama, Sıralama ve Filtreleme

- **Arama Çubuğu:** Yazdıkça listeyi ürün adına veya kategoriye göre süzer. Tek dokunuşla temizleme düğmesi vardır.
- **Sıralama Çipleri:** **Eklenme Tarihi**, **Bitiş Tarihi** ve **İsim**. Seçili çipe tekrar dokunarak sırayı tersine çevirebilirsiniz.
- **Para Birimi Filtresi:** **Tüm Ürünler**'i veya yalnızca tek bir para birimiyle kaydedilmiş ürünleri gösterir.

---

## 5. Garanti Kartları

Her kart; ürün görselini veya simgesini, ürün adını, kategorisini (Elektronik, Giyim & Moda, Ev & Yaşam, Otomotiv, Kişisel Bakım, Diğer), fiyatını ve bir geri sayım rozetini gösterir:

- **Tema rengi:** 30 gün veya daha fazla kaldı.
- **Turuncu:** 30 günden az kaldı.
- **Kırmızı:** 3 günden az kaldı. Son 24 saatte rozet saat, dakika ve saniye olarak geri sayar.
- **Koyu kırmızı:** Garantinin süresi doldu.

Ürün detayını açmak için karta dokunun; seçim modunu başlatmak için uzun basın. Garanti bitiş tarihleri, QR transferiyle gelen ek garanti süresini de içerir.

---

## 6. Ürün Ekleme (+ Düğmesi)

Sağ alt köşedeki `+` düğmesi üç seçenek sunar:

- **Elle Ekle:** Ürün adı, simge, fiyat ve para birimi, kategori, bitiş tarihi, **İade Hakkı** (gün sayısı) ve **Kullanım Yoğunluğu** alanlarını içeren form. **Belgeler ve Kanıtlar** bölümünde fatura, garanti belgesi (25 MiB'a kadar görsel veya PDF), ürün görseli ve kanıt videosu ekleyebilir, fiziksel kopyanın nerede durduğunu kaydedebilirsiniz. **Seri Giriş Modu**, kaydettikten sonra formu açık tutarak arka arkaya birden çok ürün girmenizi sağlar.
- **Garanti Yakala (Beta):** Fiş, fatura veya garanti belgesinin fotoğrafını çekin ya da seçin. Metin cihazınızda okunur; ürün adı, fiyat, para birimi ve tarihler önerilir, belgede açıkça yazmayan değerler "Tahmini" olarak işaretlenir. Kaydetmeden önce alanları mutlaka orijinal belgeyle karşılaştırın.
- **Termal Fiş Kurtarıcı:** Silikleşmiş termal fişleri kontrast ve netleştirme filtreleriyle okunabilir hâle getirir ve sonuçları kendi arşivinde saklar.

Listeyi aşağı kaydırdığınızda başa dönme düğmesi belirir.

---

## 7. Ürün Detayı

- **Belgeler:** Faturayı ve garanti belgesini tam boyutta görüntüleyin.
- **Olası İade Aktif:** Girdiğiniz iade süresinde kalan günleri gösterir. İade koşulları ülkeye ve kategoriye göre değişir.
- **Kanıt Videosu:** Zaman damgalı kanıt videosunu oynatın veya indirin.
- **Servis Geçmişi:** Başlık, açıklama ve ücret içeren servis kayıtları ekleyin.
- **Seçenekler menüsü:** **Düzenle**, **Paylaş / Satış İlanı** (hazır bir satış metnini kopyalar), **PDF Sertifikası Oluştur**, **Kanıt Videosunu Paylaş**, QR kodla başka telefona **Transfer Et (Air Gap)**, **Fiziksel Kopya Nerede?** ve **Sil** (ürünü çöp kutusuna taşır).

---

## 8. Alt Gezinme Çubuğu

- **Garantiler (Ana Sayfa):** Envanter listeniz ve Güvence Altındaki Varlıklar kartı.
- **Analiz:** Toplam Varlık Değeri, Yaklaşan Bitişler, ürün sayısı, Ortalama Garanti Ömrü, En Değerli Ürün, Kategori Dağılımı ve son 6 ayın Aylık Garanti Girişleri. Tüm hesaplamalar cihazınızda yapılır.
- **Araçlar:**
  - **Transfer Al (Air Gap):** Ürünü eklemek için gönderen telefondaki QR kodu tarayın. QR kod ürün adı, fiyat, para birimi, tarihler, ek garanti süresi ve kategori bilgilerini okunabilir biçimde taşır; fotoğraflar ve belgeler aktarılmaz.
  - **Termal Fiş Kurtarıcı**
  - **PDF Sertifikası:** Tüm ürünlerinizin PDF envanter raporunu oluşturur.
  - **Excel (CSV) Çıktısı:** Envanterinizi tablo dosyası olarak dışa aktarır.
  - **Envanter Videosu** ve **Tema & Görünüm:** Kanıt videosu özelliğine ve görünüm ayarlarına dair kısa rehberler.
- **Ayarlar:**
  - **Genel Ayarlar:** Tema Seçimi (sistem, açık, koyu), Tema Vurgusu, Animasyonlu Arka Plan, Uygulama Dili ve Bildirim Tercihleri.
  - **Veri Yönetimi:** Yedekle (Dışa Aktar), Geri Yükle (İçe Aktar), Çöp Kutusu (ürünleri geri yükleyin veya kalıcı olarak silin) ve Tüm Verileri Sıfırla (iki kez onay ister).
  - **Hakkında:** Hata Bildir & Geri Bildirim, Çökme Raporları, Yasal Koşullar & Aydınlatma ve Sürüm Bilgisi.

---

## 9. Bildirimler ve Ana Ekran Widget'ı

- **Hatırlatmalar:** Bildirim izni verirseniz Vancrone garanti bitişinden 30, 7, 3 ve 1 gün önce ve son gün, iade süresinin bitmesine 2 gün kala ve dönemsel olarak yedek almanız için hatırlatma gönderir. Zaman zaman ipuçları ve özel gün mesajları da gönderir. Bildirimlerin iletilmesi telefonunuzun pil ve bildirim ayarlarına bağlıdır.
- **Widget:** Uygulamayı açmadan kaç ürünün güvende, yaklaşan veya kritik durumda olduğunu görmek için Vancrone widget'ını ana ekranınıza ekleyin.

---

## 10. Güvenlik Notları

- **Root'lu cihazlar:** Root belirtisi tespit edilirse Vancrone bir uyarı gösterir; riski kabul ederek devam edebilir veya çıkabilirsiniz.
- **Kaybolan şifreleme anahtarı:** Telefonun şifreleme anahtarı kullanılamaz hâle gelirse Vancrone açılamayan kayıtları ayrı bir klasörde saklar ve yedekten geri yükleme ya da boş kasayla başlama seçeneği sunar.

---

## 11. Destek ve Geri Bildirim

- Hata bildirmek veya öneri göndermek için **Ayarlar > Hakkında > Hata Bildir & Geri Bildirim** menüsünü kullanın (günde en fazla iki bildirim). Mesajınız, isteğe bağlı olarak girdiğiniz e-posta adresi ve temel cihaz ile uygulama sürümü bilgileri geliştiriciye gönderilir.
- Geliştiriciye Google Play mağaza sayfasındaki doğrulanmış iletişim kanalından da ulaşabilirsiniz.
- *Spam botlarına ve otomatik tarayıcılara karşı korunmak amacıyla bu rehberde e-posta adresleri açık metin olarak yayımlanmamıştır.*
