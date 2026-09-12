# Vancrone Ana Sayfa Rehberi ve Özellik Tanıtımı

> Bu belge, Vancrone uygulamasının ana ekran mimarisini, garanti takip mekanizmasını ve güvenlik özelliklerini açıklayan resmî kullanıcı kılavuzudur. Son güncelleme: 12 Eylül 2026.

---

## 1. Genel Bakış ve Çevrimdışı (Offline-First) Mimari

Vancrone, satın aldığınız ürünlerin garanti sürelerini, faturalarını, seri numaralarını ve mülkiyet kanıtlarını güvenle takip etmeniz için tasarlanmış bağımsız bir dijital envanter ve kasa aracıdır.

- **Tamamen Çevrimdışı ve Yerel Depolama:** Vancrone, verilerinizi hiçbir harici sunucuya veya bulut veritabanına göndermez. Google Drive API gibi harici servis bağımlılıkları tamamen kaldırılmıştır.
- **Şifreli Yerel Kasa:** Tüm ürün bilgileri, fatura görselleri ve kayıtlar cihazınızın güvenli depolama alanında Room SQLCipher ile şifrelenmiş olarak saklanır.
- **Kullanıcı Sorumluluğu ve Yedekleme:** Verileriniz tamamen cihazınızda yer aldığından; cihazın kaybolması, sıfırlanması veya arızalanması durumunda veri kaybı yaşamamak için **Ayarlar > Veri Güvenliği ve Yedekleme** menüsünden şifreli `.vcb` yedek dosyanızı düzenli olarak dışa aktarmanız önerilir. Geliştiricinin kaybolan cihaz verilerine erişmesi veya geri getirmesi teknik olarak mümkün değildir.

---

## 2. Üst Menü ve Hızlı Erişim Çubuğu

Ana sayfanın üst kısmında yer alan Vancrone Üst Çubuğu (Top Bar), hızlı navigasyon ve toplu yönetim araçlarını barındırır:

- **Uygulama Başlığı ve Plan Rozeti:** Tıklandığında listeyi en başa sarar. Aktif paket durumunuza göre (PRO / BUSINESS) özel rozet gösterilir.
- **Takvim Görünümü:** Sağ üstteki takvim simgesi ile garanti bitişlerini aylık takvim matrisi üzerinde görsel olarak takip edebilirsiniz.
- **Sıkça Sorulan Sorular (SSS):** Soru işareti simgesi ile kullanım ipuçlarına ve rehberlere doğrudan ulaşabilirsiniz.
- **Toplu Seçim ve Yönetim Modu:** Herhangi bir garanti kartına uzun bastığınızda liste çoklu seçim moduna geçer. Birden fazla ürünü tek dokunuşla seçip topluca çöp kutusuna taşıyabilirsiniz.

---

## 3. Çoklu Para Birimi Güvence & Varlık Kartı

Ana ekranın en üstünde yer alan dinamik gradyan kart, güvence altındaki toplam finansal varlığınızı özetler:

- **Birincil Para Birimi Toplamı:** Ayarlarınızda seçtiğiniz ana para birimine (örn. ₺, $, €, ¥) göre kayıtlı ürünlerinizin toplam maliyetini anlık olarak hesaplar.
- **Çoklu Para Birimi Detayları:** Karta dokunduğunuzda açılan panel, farklı para birimleriyle (EUR, USD, GBP vb.) kaydettiğiniz tüm harcamaların dökümünü ayrı ayrı listeler.
- **Güvenlik Rozeti:** Kasanızın donanımsal ve yazılımsal olarak yerel koruma altında olduğunu simgeler.

---

## 4. Arama, Filtreleme ve Dinamik Sıralama

Geniş envanterlerde aradığınız ürünü saniyeler içinde bulmanızı sağlayan akıllı araçlar:

- **Canlı Arama Çubuğu:** Ürün adı, mağaza veya seri numarası yazıldıkça sonuçları anında filtreler. Yanındaki temizle butonu ile aramayı anında sıfırlayabilirsiniz.
- **Sıralama Çipleri (Sort Chips):**
  - **Eklenme Tarihi:** Ürünleri kasanıza ekleme sırasına göre artan veya azalan şekilde listeler.
  - **Bitiş Tarihi:** Süresi en yakın dolacak ürünleri en üste getirerek garanti haklarınızı kaçırmamanızı sağlar.
  - **İsim:** Ürünleri A'dan Z'ye veya Z'den A'ya alfabetik olarak dizer.
- **Para Birimi Filtresi:** Yalnızca belirli bir para birimiyle kaydedilen ürünleri (örn. sadece USD veya sadece EUR) görüntülemenizi sağlayan açılır filtre çipi.

---

## 5. Akıllı Garanti ve Envanter Kartları

Her ürün kartı, ihtiyacınız olan tüm kritik verileri tek bakışta sunar:

- **Görsel Kimlik:** Ürünün gerçek fotoğrafı veya kategoriye özel renkli simge.
- **Ürün Bilgileri:** Ürün adı, ait olduğu kategori (Elektronik, Giyim, Ev & Yaşam, Otomotiv, Kişisel Bakım, Diğer) ve satın alma fiyatı.
- **Akıllı Süre Rozeti (Dinamik Renk Kodlu):**
  - **Yeşil / Vurgu:** 30 günden fazla süresi olan güvenli garantiler.
  - **Turuncu:** Son 30 gün içine girmiş, yaklaşan bitişler.
  - **Kırmızı:** Son 3 gün! Son 24 saat içinde ise canlı geri sayım (saat, dakika, saniye) devreye girer.
  - **Bordo / Koyu Kırmızı:** Süresi dolmuş ürünler.
- **Hızlı İşlemler:** Karta tek dokunuşla ayrıntılı inceleme sayfasına (fatura fotoğrafları, seri numarası, barkod, garanti şartları) geçebilir, uzun basarak toplu seçim yapabilirsiniz.

---

## 6. Hızlı Aksiyon Butonu (FAB)

Ekranın sağ alt köşesindeki genişleyebilen `+` butonu ile yeni kayıtlar oluşturabilirsiniz:

- **Elle Ekle:** Ürün adı, kategori, satın alma tarihi, garanti süresi, ek garanti, iade hakkı, seri no ve fatura fotoğraflarını adım adım ekleyebileceğiniz kapsamlı form.
- **Fiş Kurtarıcı:** Termal kağıtlarda zamanla silinen ve solan faturaları akıllı filtrelerle netleştiren ve okunabilirliğini geri kazandıran özel restorasyon aracı.
- **Yukarı Kaydır (Scroll to Top):** Listeyi aşağı kaydırdığınızda sol altta beliren hızlı başa dön butonu.

---

## 7. Yüzen Alt Gezinme Çubuğu (Bottom Navigation)

Ekranın altında zarifçe süzülen oval menü ile uygulamanın temel bölümleri arasında geçiş yapabilirsiniz:

- **Garantiler (Ana Sayfa):** Tüm envanterinizin listelendiği ana kontrol merkezi.
- **Analiz:** Harcama dağılımları, kategori oranları ve etkileşimli aylık garanti girişleri çizgi grafiği.
- **Araçlar:** QR/Barkod okuyucu, cihazlar arası P2P garanti transferi, video envanter turu ve çöp kutusu.
- **Ayarlar:** Tema rengi, para birimi seçimi, SAF ile şifreli `.vcb` yedekleme ve geri yükleme.

---

## 8. Destek ve Hata Bildirimi

Vancrone ile ilgili bir sorun yaşarsanız, öneriniz varsa veya bir hata bildirmek isterseniz:

- Uygulama içerisinden **Ayarlar > Hakkında > Hata Bildir & Geri Bildirim** menüsünü kullanabilirsiniz.
- Form aracılığıyla gönderdiğiniz geri bildirimler doğrudan geliştirici ekibine güvenle iletilir.
- Ayrıca resmî Google Play mağaza sayfamız üzerinden geliştiriciye ulaşabilirsiniz.
- *Spam ve otomatik botları önlemek amacıyla belgelerimizde e-posta adresi açık metin olarak yayınlanmamaktadır.*
