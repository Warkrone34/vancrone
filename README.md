# valura-privacy

# VALURA – GİZLİLİK POLİTİKASI, KULLANICI SÖZLEŞMESİ VE AYDINLATMA METNİ
**Son Güncelleme Tarihi:** 05.08.2026  
**Yürürlük Tarihi:** 05.08.2026  

---

## BÖLÜM 1: GİZLİLİK POLİTİKASI VE VERİ GÜVENLİĞİ (KVKK, GDPR & GOOGLE PLAY DATA SAFETY)

### 1.1. Çevrimdışı Öncelikli (Offline-First) Veri Mimarisi ve Yerel Depolama
Valura ("Uygulama"), kullanıcılarının kişisel verilerinin ve finansal mahremiyetinin korunmasını en temel öncelik olarak kabul eder. Uygulama **"Offline-First" (Çevrimdışı Öncelikli)** prensibiyle tasarlanmıştır.
* **Sunucusuz Mimari:** Uygulamaya kaydettiğiniz ürün adları, fatura fotoğrafları, garanti belgeleri, satın alma tarihleri, garanti bitiş süreleri, fiyat bilgileri, servis geçmişi ve kişisel notlar **KESİNLİKLE Geliştiriciye ait veya üçüncü şahısların kontrolündeki herhangi bir harici bulut sunucusuna iletilmez, satılmaz ve kiralanmaz.**
* **Askeri Standartta Yerel Şifreleme (AES-256):** Tüm verileriniz, cihazınızın dahili hafızasında `valura_secure_v2.db` ve `valura_kasa` adlarıyla **SQLCipher** ve **EncryptedSharedPreferences** teknolojileri kullanılarak 256-bit AES (Advanced Encryption Standard) algoritmasıyla şifrelenir. Cihazınız kaybolsa, çalınsa veya dosya sistemine dışarıdan müdahale edilse dahi şifrelenmiş veritabanı içeriği üçüncü kişilerce okunamaz.

### 1.2. İsteğe Bağlı Google Drive Bulut Yedekleme
Kullanıcılar, cihaz değişikliği veya donanım arızası durumlarında verilerini kurtarabilmek için uygulama ayarlarından "Google Drive Bulut Yedekleme" özelliğini kendi açık rızalarıyla etkinleştirebilir.
* **Kişisel Alan İzolasyonu:** Bu özellik çalıştırıldığında; garanti kayıtlarınız ve belge görselleriniz şifrelenmiş bir `.zip` arşivi halinde **doğrudan ve yalnızca kullanıcının kendi kişisel Google Drive hesabının gizli uygulama klasörüne (`appDataFolder`)** yüklenir.
* **Geliştirici Erişimsizliği:** Geliştirici ekip, Google Drive hesabınıza, bulut depolama alanınıza, kimlik doğrulama şifrelerinize veya Drive üzerindeki yedek dosyalarınızın içeriğine hiçbir şekilde erişemez ve görüntüleyemez.
* **Kota Koruması:** Google Drive bulut yedeklemesi yalnızca garanti belgelerini, fatura görsellerini ve metin verilerini kapsar; yüksek dosya boyutuna sahip envanter kanıt videoları (`videoKanitYolu`) kullanıcının bulut kotasını tüketmemek adına yedeklemeye dâhil edilmez ve yalnızca cihazın yerel hafızasında saklanır.

### 1.3. Cihaz İzinleri ve İşlenme Amaçları
Valura, temel işlevlerini yerine getirebilmek adına aşağıdaki sistem izinlerini talep eder:
* **Kamera İzni (`CAMERA`):** Fatura fotoğraflarını çekmek, yerel OCR taraması yapmak, ürün görseli eklemek ve envanter kanıt videosu kaydetmek amacıyla kullanılır. Çekilen görseller anında yerel kasaya alınır.
* **Mikrofon / Ses Kaydı İzni (`RECORD_AUDIO`):** Yalnızca kullanıcının envanter kanıt videosu çekerken ürün durumunu sesli olarak betimleyebilmesi amacıyla, video kaydıyla eşzamanlı olarak kullanılır. Arka planda gizli ses kaydı veya dinleme kesinlikle yapılmaz.
* **Galeri ve Medya İzni (`READ_MEDIA_IMAGES` / `READ_EXTERNAL_STORAGE`):** Cihaz galerisindeki mevcut fatura görsellerinin ve belgelerin seçilerek uygulamanın yerel veritabanına aktarılması amacıyla kullanılır.
* **Bildirim İzni (`POST_NOTIFICATIONS`):** Garanti süresi yaklaşan ürünlerin, yasal iade sürelerinin (14 gün) ve bakım zamanlarının kullanıcıya hatırlatılması amacıyla kullanılır. Bildirimler tamamen cihaz içerisindeki yerel zamanlayıcılar (`WorkManager`) tarafından tetiklenir; dış bir sunucudan anlık push bildirimi gönderilmez.
* **Konum İzni (`ACCESS_FINE_LOCATION`):** Yalnızca kullanıcının rızasıyla, eklenen envanterin veya faturanın kaydedildiği konumu (ev, ofis, mağaza vb.) yerel olarak etiketlemek amacıyla kullanılır. Konum bilgileri dış sunuculara veya takip sistemlerine iletilmez.

### 1.4. Üçüncü Taraf SDK'lar, Analitik ve Reklam Servisleri
Valura, uygulamanın kararlılığını sağlamak ve sürdürülebilirliğini desteklemek amacıyla uluslararası standartlarda güvenilir üçüncü taraf hizmet sağlayıcılarla entegre çalışır:
* **Google Firebase Crashlytics:** Uygulamada beklenmeyen bir çökme (crash) meydana geldiğinde, hatanın çözülebilmesi amacıyla anonim çökme logları, hata yığınları (stack trace), cihaz modeli ve işletim sistemi versiyonu gibi kimlik tanımlamayan teknik metrikleri toplayıp geliştiriciye iletir. Hiçbir kişisel veri, ürün adı veya fatura görseli bu loglara dâhil edilmez.
* **Google AdMob (`MobileAds`):** Uygulamanın ücretsiz veya reklamlı kullanım senaryolarında Google AdMob servisleri çalışır. AdMob, reklam frekansının denetlenmesi ve gösterimi için Google Reklam Kimliği'ni (Advertising ID) ve çerez metriklerini Google'ın gizlilik politikalarına uygun olarak işleyebilir. (Uygulamanın ücretsiz lansman modunda `IS_FREE_LAUNCH_MODE` aktif olduğu dönemlerde reklam gösterilmese dahi altyapı bu standartlara tabidir).
* **Google ML Kit (`GmsDocumentScanning`):** Fatura metinlerini ve tarihleri okumak amacıyla kullanılan optik karakter tanıma (OCR) kütüphanesidir. İşlemler tamamen cihaz üzerinde (on-device) gerçekleşir, taranan resimler dışarıya aktarılmaz.

---

## BÖLÜM 2: KULLANICI SÖZLEŞMESİ VE ANTİ-THEFT (TERSİNE MÜHENDİSLİK YASAĞI)

### 2.1. Hizmetin Niteliği ve "Olduğu Gibi" (AS IS) Beyanı
* Valura, kullanıcıların kendi girdikleri faturaları ve garanti sürelerini kolayca takip etmelerini sağlayan dijital bir asistandır. 
* Uygulama "OLDUĞU GİBİ" (AS IS) esasıyla sunulmaktadır. Cihazın bozulması, işletim sistemi güncellemesi, uygulamanın kullanıcı tarafından silinmesi veya fiziksel depolama arızaları nedeniyle yaşanabilecek yerel veri kayıplarından Geliştirici sorumlu tutulamaz. Kullanıcının düzenli olarak "ZIP Yedek Al" veya "Google Drive Yedekleme" özelliklerini kullanması önerilir.

### 2.2. Tersine Mühendislik, Uygulama Kopyalama ve Siber Güvenlik Yasağı (Anti-Theft)
Valura'nın tüm kaynak kodları, arayüz tasarımları (UI/UX), veritabanı şemaları (`ValuraDatabase`), görsel varlıkları, şifreleme altyapısı ve iş mantığı uluslararası telif hakları ve fikri mülkiyet kanunları ile korunmaktadır.
Kullanıcı, işbu Sözleşme'yi kabul ederek aşağıdaki eylemleri KESİNLİKLE YAPMAYACAĞINI kabul, beyan ve taahhüt eder:
1. Uygulamanın kaynak kodunu decompile etmek, dis-assemble etmek, tersine mühendislik (reverse engineering) yapmak veya kopyalamak,
2. Uygulamanın arayüz tasarımını, özelliklerini, algoritmalarını veya konseptini taklit ederek rakip, klon veya türev bir yazılım geliştirmek,
3. Uygulama içerisindeki Google Play Billing lisans kontrolü, in-app review, şifreleme veya veri bütünlüğü doğrulama mekanizmalarını devre dışı bırakmaya veya atlatmaya çalışmak,
4. Uygulamayı zararlı yazılımlar, otomatik botlar veya manipülatif komutlarla engellemek veya bozmak.
* **Yaptırım:** İşbu maddelerin ihlali halinde Geliştirici; Fikir ve Sanat Eserleri Kanunu, Türk Ticaret Kanunu ve ilgili uluslararası hukuki yaptırımlar uyarınca doğacak tüm doğrudan ve dolaylı maddi/manevi zararları ihlal eden taraftan tazmin ettirme hakkını saklı tutar.

### 2.3. Root / Jailbreak ve İşletim Sistemi Güvenliği
Valura, kullanıcı verilerini AES-256 standardıyla yerel hafızada şifreleyerek saklar. Cihazın işletim sistemi yetkilerinin kırılmış olması (Root, Jailbreak, Magisk kullanımı, Custom ROM / `test-keys` entegrasyonu veya yetkisiz `su` komutu erişimi), cihazın şifreleme anahtarlarını (`MasterKey`) savunmasız bırakır. Valura, kullanıcı mahremiyetini korumak amacıyla bu tür güvenlik ihlali tespit edilen cihazlarda çalışmayı reddetme hakkına sahiptir.

---

## BÖLÜM 3: AYDINLATMA METNİ, YEREL OCR VE SORUMLULUK SINIRLAMASI

### 3.1. Sigorta ve Garanti Otoritesi Reddi
* **VALURA BİR SİGORTA ŞİRKETİ, RESMİ GARANTÖR, HUKUKİ ARABULUCU VEYA ÜRÜN SATICISI DEĞİLDİR.**
* Valura, yalnızca kullanıcının girdiği tarihler ve belgeler üzerinden organizasyon sağlayan dijital bir ajandadır.

### 3.2. Yerel OCR (Fatura Tarama) Yanılsaması ve Doğrulama Yükümlülüğü
* Uygulama içerisinde sunulan Optik Karakter Tanıma (OCR) ve Fiş Kurtarıcı özellikleri, Google ML Kit aracılığıyla tamamen cihaz üzerinde çalışır.
* Faturanın yıpranmış olması, ışık yansıması, yazı tipi, baskı kalitesi veya kamera açısı nedeniyle OCR motorunun ürün adını, satın alma tarihini, fiyatı veya garanti süresini **hatalı okuması, eksik çıkarması veya yanlış metin üretmesi mümkündür.**
* **DOĞRULAMA YÜKÜMLÜLÜĞÜ:** KULLANICI, OCR TARAMASI TARAFINDAN OTOMATİK DOLDURULAN TÜM ALANLARI KAYDETMEDEN ÖNCE GÖZLE KONTROL ETMEK VE DOĞRULAMAKLA YÜKÜMLÜDÜR. Yanlış veya eksik aktarılan fatura tarihleri nedeniyle yaşanabilecek garanti süresi kayıplarından Geliştirici hiçbir şekilde sorumlu tutulamaz.

### 3.3. Bildirimler ve Hukuki Hak Kayıplarına İlişkin Sorumluluk Reddi
* Uygulamanın; garanti bitiş hatırlatmalarını (`GarantiBildirimWorker`), 14 günlük yasal iade süresi uyarılarını veya motivasyon bildirimlerini zamanında göndermemesi, cihazın pil tasarruf modları (`Doze Mode`), arka plan kısıtlamaları veya donanım gecikmeleri nedeniyle bildirimlerin ulaşmaması yahut kullanıcının bildirimi gözden kaçırması mümkündür.
* Bu nedenlerle kullanıcının yasal garanti süresini, ücretsiz tamir hakkını veya ürün iade süresini kaçırması sonucu doğabilecek doğrudan veya dolaylı maddi/manevi zararlardan, hak kayıplarından Geliştirici sorumlu değildir. Tüm yasal takvim takibi ve fiziki belge saklama yükümlülüğü münhasıran Kullanıcıya aittir.

### 3.4. Yapay Zeka Geliştirme Beyanı ve Fikri Mülkiyet Sınırlandırması
Geliştirici, işbu Sözleşme kapsamındaki yazılımın ve kod yapılarının geliştirilmesinde yapay zeka destekli araçlardan yararlanabileceğini beyan eder. 
* Geliştirici, teslim ettiği iş üzerinde **yalnızca kendisine ait devredilebilir nitelikteki hakları** Kullanıcıya sağlamaya yetkili olduğunu taahhüt eder. 
* Geliştirici, **kendi bilgisi dâhilinde** uygulamanın üçüncü kişilerin fikri mülkiyet haklarını ihlal etmediğini beyan eder; ancak yapay zeka çıktılarının hukuki koruma kapsamının uluslararası yargı kararları ve değişen mevzuat çerçevesinde değişkenlik gösterebileceğini taraflar kabul eder. 
* Geliştiricinin işbu sözleşmeden doğabilecek toplam mali sorumluluğu, Kullanıcının uygulamaya fiilen ödediği tutarla sınırlıdır. Ücretsiz kullanım modellerinde Geliştiricinin herhangi bir tazminat yükümlülüğü bulunmamaktadır.

---

## BÖLÜM 4: KVKK VE GDPR KULLANICI HAKLARI (VERİ SİLME)

Valura, hiçbir kişisel verinizi merkezi bir sunucuda barındırmadığı için, verileriniz üzerindeki mutlak kontrol tamamen sizin elinizdedir.
* **Kalıcı Silme:** Uygulama içerisindeki **"Ayarlar > Verileri SIFIRLA"** seçeneğini kullanarak veya uygulamayı cihazınızdan kaldırarak; cihazınızda saklanan tüm garanti belgelerini, fatura görsellerini, kanıt videolarını ve şifreli yerel veritabanını **saniyeler içinde, geri dönülmez şekilde kalıcı olarak yok edebilirsiniz.**
* **İletişim:** KVKK madde 11 ve GDPR uyarınca yasal talepleriniz, geri bildirimleriniz ve aydınlatma sorularınız için resmi destek kanalımız üzerinden bizimle iletişime geçebilirsiniz:  
  📧 **E-Posta:** `destek@valura.app`

---

## BÖLÜM 5: UYGULANACAK HUKUK VE YETKİLİ MAHKEME

İşbu Sözleşme'nin yorumlanmasında ve uygulanmasında **Türkiye Cumhuriyeti Kanunları** geçerlidir. Sözleşmeden veya Uygulamanın kullanımından doğabilecek her türlü hukuki uyuşmazlığın çözümünde **İstanbul Mahkemeleri ve İcra Daireleri** kesin yetkilidir.
