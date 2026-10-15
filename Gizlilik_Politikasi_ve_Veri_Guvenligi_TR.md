# Gizlilik Politikası ve Veri Güvenliği

> Bu belge, Vancrone uygulamasının veri işleme prensiplerini, güvenlik tedbirlerini ve gizlilik standartlarını düzenleyen Türkçe politika metnidir. Son güncelleme: 15 Ekim 2026.

## 1. Giriş

Bu Gizlilik Politikası, Geliştiricinin Vancrone Android uygulamasıyla bağlantılı olarak bilgileri nasıl ele aldığını açıklar. Bu politikayı temel bir ilke üzerine kurduk: Biz, yani Geliştirici, kişisel envanterinizi, garanti belgelerinizi, faturalarınızı veya fotoğraflarınızı görmüyoruz ve toplamıyoruz. Bu politika, bu durumun tam olarak ne anlama geldiğini; uygulamaya entegre Google hizmetleri aracılığıyla toplanan sınırlı teknik verileri ve geri bildirim formuyla kendi isteğinizle gönderdiğiniz bilgileri açıklar.

Sorumluluk Kimde: Vancrone, bu politikada "Geliştirici" olarak anılan bağımsız bir bireysel geliştirici tarafından yayımlanır. Geliştiriciye vancrone.app@gmail.com adresinden ulaşabilirsiniz; Google tarafından doğrulanan yayıncı bilgileri Google Play mağaza sayfasında gösterilmektedir. Garanti kayıtlarınız, faturalarınız ve fotoğraflarınız münhasıran kendi cihazınızın yerel depolama alanında saklandığından, Geliştirici bu içeriği hiçbir zaman uzaktan almaz ve bu içerik bakımından veri sorumlusu olarak hareket etmez. Geliştirici yalnızca 6., 7. ve 14. bölümlerde açıklanan sınırlı veriler bakımından veri sorumlusudur: çökme raporları, geri bildirim formuyla gönderdiğiniz mesajlar ve uygulama içi satın alma sunulursa Google Play'in sağladığı satın alma kayıtları.

## 2. Yaklaşımımız: Tasarımı Gereği Önce Yerel (Offline-First)

Vancrone, "önce çevrimdışı" (offline-first) bir mimari üzerine kurulmuştur. Uygulamaya girdiğiniz ürün bilgilerini, fiyatları, tarihleri, notları, fatura fotoğraflarını veya kasa kanıt videolarını saklayan, dizinleyen ya da bunlara erişebilen merkezî bir Vancrone sunucusu yoktur. Bu durum bilinçli bir mimari tercihtir ("tasarımı gereği gizlilik").

## 3. Toplamadığımız Veriler

Aşağıdakileri kesinlikle toplamıyor, iletmiyor, görüntülemiyor, satmıyor, kiralamıyor veya bunlara erişmiyoruz:

- Ürün envanteri ve garanti kayıtlarınız (adlar, fiyatlar, tarihler, iade süreleri, servis kayıtları, notlar);
- Fatura, fiş fotoğraflarınız veya kasa kanıt videolarınız;
- Uygulamanın sizin için yerel olarak oluşturduğu finansal risk ve garanti durum özetleri.

Bu veriler tamamen sizin tarafınızdan oluşturulur ve siz bunları kendiniz dışa aktarana kadar yalnızca cihazınızın yerel belleğinde kalır.

## 4. Cihazınızda Yerel Olarak Saklanan Veriler

Kayıtlarınız (ürün adları, fiyatlar, tarihler, iade süreleri, servis kayıtları ve fiziksel belgelerin nerede durduğuna ilişkin notlar) cihazınızdaki yerel bir veritabanında SQLCipher ile AES-256 şifrelenerek saklanır. Veritabanı anahtarı cihazınızda üretilir ve Android Keystore'daki (destekleyen cihazlarda donanım destekli) bir anahtarla korunan EncryptedSharedPreferences içinde tutulur. Fatura fotoğrafları, ürün görselleri ve kanıt videoları ise uygulamanın özel depolama alanında saklanır; bu alan Android tarafından diğer uygulamalardan yalıtılır ve cihazın kendi depolama şifrelemesiyle korunur, ancak Vancrone bu medya dosyalarına ayrıca bir şifreleme katmanı uygulamaz. Root'lu cihazlarda diğer uygulamalar bu korumaları aşabilir.

## 5. Storage Access Framework (SAF) ile Şifreli Manuel Yedekleme

Vancrone herhangi bir Google Drive API senkronizasyonu veya merkezi bulut yedekleme sunucusu barındırmaz. Bunun yerine, verilerinizi yedekleyebilmeniz için Android'in Storage Access Framework (SAF) altyapısını kullanır:

- Manuel Dışa Aktarma: Ayarlar menüsünden yedek aldığınızda; yerel veritabanınız, garanti medyalarınız (fatura fotoğrafları, ürün görselleri, kanıt videoları) ve Termal Fiş Kurtarıcı ile kaydettiğiniz görseller tek bir arşivde toplanır ve AES-256-GCM ile şifrelenerek tek bir dosya (.vcb) haline getirilir.
- İsteğe Bağlı Yedek Parolası: Yedek parolası belirlerseniz şifreleme anahtarı bu paroladan türetilir (PBKDF2-HMAC-SHA256, 600.000 tekrar) ve dosya parola olmadan açılamaz. Unutulan parolayı Geliştirici kurtaramaz. Parola belirlemezseniz dosya uygulamaya gömülü bir anahtarla şifrelenir: yedeği yine her cihazda geri yükleyebilirsiniz, ancak dosyayı ve Vancrone uygulamasını birlikte ele geçiren herkes de açabilir. Özellikle yedeği paylaşılan bir konumda veya bulut depolamada saklıyorsanız parola belirlemenizi öneririz.
- Tam Kullanıcı Denetimi: Bu dosya yalnızca sizin SAF iletişim penceresinde belirlediğiniz konuma (cihaz hafızası, SD kart, USB bellek veya bilgisayarınız) kaydedilir.
- Geliştiricinin Erişimi Yoktur: Bu yedek dosyası Vancrone tarafından Geliştiricinin veya herhangi bir üçüncü tarafın sunucusuna iletilmez. Yedeğin saklanması, harici ortamlara aktarılması ve korunması tamamen kullanıcının sorumluluğundadır.

## 6. Vancrone'un Kullandığı Üçüncü Taraf Hizmetler

Vancrone, çalışabilmek için Google tarafından sağlanan sınırlı sayıda resmi SDK'ya dayanır. Bu SDK'ların gönderdiği veriler, Google tarafından Geliştirici adına Google'ın veri işleme şartları kapsamında işlenir.

- Google Firebase Crashlytics — Çökme Raporlama: Uygulama çöktüğünde veya ele alınan bir hata oluştuğunda (örneğin PDF ya da CSV dışa aktarımı başarısız olduğunda) Crashlytics; hata yığınını (stack trace), cihaz modelini, Android sürümünü, uygulama sürümünü, rastgele bir Crashlytics kurulum kimliğini ve olayın zamanını içeren bir rapor gönderir. Raporlar kayıtlarınızı, faturalarınızı veya fotoğraflarınızı içermez ve adınızla ya da e-posta adresinizle ilişkilendirilmez. Yalnızca hataları gidermek için kullanılır ve Crashlytics tarafından 90 gün saklanır.
- Google AdMob — Reklam (planlanan): Vancrone'un mevcut sürümü reklam göstermez ve Google Mobile Ads (AdMob) SDK'sını içermez. Gelecekte ücretsiz sürüme reklam eklenirse bu politika o sürümden önce güncellenecek ve kişiselleştirilmiş reklamlar, yasanın gerektirdiği durumlarda yalnızca onayınızla gösterilecektir.
- Google ML Kit — Cihaz Üzerinde Fatura Tarama (OCR) ve Belge Tarayıcı: Fatura tarayıcısı, Google ML Kit'in tamamen cihaz üzerinde (on-device) çalışan metin tanıma modülünü ve Google Play hizmetlerinin belge tarayıcısını kullanır. Taranan görseller ve metinler cihazınızda işlenir, Google sunucularına yüklenmez. ML Kit; model güncellemelerini indirmek ve API'nin kendi performansına ilişkin sınırlı ölçümleri göndermek için Google ile iletişim kurabilir; bu ölçümler görsellerinizi veya metinlerinizi içermez.
- Google Play Faturalandırma — Satın Alımlar: Vancrone'un mevcut sürümü uygulama içi satın alma sunmaz ve Google Play Faturalandırma'ya bağlanmaz. İsteğe bağlı Pro veya Business yükseltmeleri sunulursa tamamen Google Play üzerinden işlenir: ödeme bilgileri yalnızca Google tarafından işlenir, Geliştirici yalnızca Google Play'in sağladığı sipariş bilgilerini (sipariş numarası, ürün, satın alma tarihi ve ülke gibi) alır ve uygulama satın alma durumunuzu cihaz üzerinde Google Play Faturalandırma Kitaplığı aracılığıyla okur. Bu politika o değişiklikten önce güncellenecektir.

## 7. Sunucu Tarafı Altyapı Yok; Geri Bildirim Formu

Vancrone kendine ait herhangi bir sunucu işletmez. Geliştirici; kayıtlarınız için hiçbir bulut arka ucu (backend), kullanıcı hesabı veya uzak veritabanı çalıştırmaz. 6. bölümde açıklanan Google hizmetleri dışında cihazınızdan yalnızca sizin başlattığınız durumlarda veri çıkar:

- Geri Bildirim Formu: Ayarlar > "Hata Bildir & Geri Bildirim" üzerinden mesaj gönderdiğinizde; mesajınız (en fazla 500 karakter), isteğe bağlı olarak girdiğiniz e-posta adresi, cihaz üreticisi ve modeli, Android sürümü, uygulama sürümü ve gönderim zamanı HTTPS üzerinden Geliştiricinin Google altyapısında çalıştırdığı bir Google Apps Script uç noktasına iletilir. Bu bilgiler yalnızca size yanıt vermek ve bildirilen sorunu gidermek için kullanılır ve bu amaç için gerektiği süre boyunca saklanır. Lütfen geri bildirim mesajlarına hassas kişisel veri yazmayın.
- Dışa Aktarma ve Paylaşım: PDF/CSV raporları, yedekler ve paylaştığınız dosyalar yalnızca sizin seçtiğiniz hedefe gider.

## 8. Güvenlik Önlemleri

Yerel AES-256 veritabanı şifrelemesinin yanı sıra; SQL enjeksiyonuna karşı parametreli veritabanı sorguları kullanılır, görseller yerel OCR motoruna verilmeden önce cihazda çözülüp küçültülür, yedekler geri yüklenmeden önce bütünlükleri doğrulanır (kimlik doğrulamalı AES-GCM şifreleme ve arşivdeki dosyaların SHA-256 özetleri) ve cihazda root belirtisi tespit edilirse uyarı gösterilir. Mevcut sürüm satın alma sunmaz; satın alma eklenirse durumu Google Play Faturalandırma Kitaplığı aracılığıyla Google Play'den okunur ve Vancrone satın alma imzalarını kendi sunucusunda ayrıca doğrulamaz. Hiçbir dijital güvenlik tedbiri mutlak koruma sağlayamayacağından, cihaz güvenliğinizi sağlamak sizin sorumluluğunuzdadır.

## 9. Veri Saklama ve Kontrolünüz

Verileriniz cihazınızda bulunduğu için tüm kontrol sizdedir:

- Uygulama içi "Tüm Verileri Sıfırla": Yerel şifreli veritabanındaki tüm garanti kayıtlarınızı, bunlara bağlı fatura fotoğrafları, ürün görselleri ve kanıt videolarıyla birlikte kalıcı ve geri döndürülemez biçimde siler. Termal Fiş Kurtarıcı ile kaydedilen görselleri ve uygulamanın özel depolama alanında herhangi bir kayda bağlı olmadan kalmış medya dosyalarıyla geçici kamera dosyalarını da siler.
- Uygulamayı kaldırmak: Cihaz işletim sistemi tarafından uygulamanın tüm yerel verilerinin kalıcı olarak silinmesini sağlar.
- Geliştirici kayıtlarınızın hiçbir kopyasına sahip olmadığından, silinen kayıtların kurtarılması mümkün değildir. Dışa aktardığınız yedek dosyaları siz silene kadar kaydettiğiniz yerde kalır.
- Çökme raporları ve geri bildirim mesajları yalnızca 6. ve 7. bölümlerde belirtilen süreler boyunca saklanır.

## 10. Çocukların Gizliliği

Vancrone 13 yaşından küçük çocuklara yönelik değildir ve çocuklardan bilerek kişisel veri toplanmaz.

## 11. Kullanıcı Seçenekleri

- Reklamlar ve Reklam Kimliği: Mevcut sürüm reklam göstermez ve Reklam Kimliğinizi toplamaz.
- Çökme Raporları: Crashlytics'i dilediğiniz zaman Ayarlar > Hakkında > "Çökme Raporları" anahtarından kapatabilirsiniz. Anahtar varsayılan olarak açıktır. Kapalıyken çökme raporu gönderilmez ve cihazınızda bekleyen raporlar silinir; tercihiniz siz değiştirene kadar korunur. Anahtarı kapatmadan önce gönderilen raporlar 6. bölümde belirtilen süre boyunca saklanır. Uygulamayı kaldırmak da tüm veri toplamayı durdurur.
- Yedekleme: Ayarlar menüsünden dilediğiniz zaman Storage Access Framework (SAF) ile şifreli yedek (.vcb) alabilir, yedeğinizi parolayla koruyabilir veya mevcut yedeğinizi geri yükleyebilirsiniz.
- Veri İmhası: Dilediğiniz an Ayarlar > "Tüm Verileri Sıfırla" adımıyla verilerinizi sıfırlayabilirsiniz.

## 12. Uluslararası Veri Aktarımları

Entegre Google hizmetleri küresel ölçekte çalıştığından, 6. ve 7. bölümlerde sayılan çökme raporları ve geri bildirim mesajları ile satın alma sunulursa Google Play sipariş verileri, Google tarafından Amerika Birleşik Devletleri dâhil olmak üzere kendi ülkenizin dışında işlenebilir. Google bu aktarımlarda, Standart Sözleşme Maddeleri (SCC) ve uygulanabildiği durumlarda AB-ABD Veri Gizliliği Çerçevesi dâhil olmak üzere kendi veri işleme şartlarına dayanır.

## 13. Gizlilik Haklarınız

Yürürlükteki veri koruma mevzuatları (KVKK, GDPR, CCPA, APPI) kapsamında; erişim, düzeltme, silme ve itiraz gibi haklarınız bulunmaktadır. Kullanıcı İçeriğiniz doğrudan sizin cihazınızda bulunduğundan, bu içeriğe ilişkin erişim, düzeltme ve silme haklarını doğrudan uygulama üzerinden kendiniz kullanabilirsiniz. Çökme raporları veya geri bildirim mesajları için vancrone.app@gmail.com adresine yazabilirsiniz; çökme raporları takma adlı (pseudonymous) olduğundan, Geliştirici hangi kayıtların size ait olduğunu belirleyemeyebilir.

## 14. Bölgeye Özgü Gizlilik Bilgileri

- Avrupa Ekonomik Alanı, Birleşik Krallık ve İsviçre: Çökme tanılaması (uygulamayı kararlı tutmak) ile gönderdiğiniz geri bildirimlerin yanıtlanması için meşru menfaat, uygulama içi satın alma sunulursa satın alımlar için sözleşmenin ifası hukuki sebeplerine dayanılır. Kişiselleştirilmiş reklam eklenirse açık rızanıza dayanacaktır. Meşru menfaate dayalı işlemeye itiraz etme ve yerel veri koruma otoritenize başvurma hakkınız saklıdır.
- Amerika Birleşik Devletleri: Geliştirici, California Tüketici Gizliliği Yasası (CCPA) kapsamında kişisel bilgileri satmaz veya paylaşmaz.
- Japonya: Kişisel Bilgilerin Korunması Kanunu (APPI) kapsamındaki haklarınız saklıdır.
- Türkiye: 6698 sayılı KVKK kapsamındaki haklarınız saklıdır; veri sorumlusu sıfatıyla Geliştiriciye vancrone.app@gmail.com adresinden ulaşabilirsiniz.

Geliştirici bağımsız bir bireysel geliştirici olduğundan, e-postalara makul bir süre içinde ve geliştirme olanakları çerçevesinde yanıt verilmektedir.
