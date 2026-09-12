# Gizlilik Politikası ve Veri Güvenliği

> Bu belge, Vancrone uygulamasının veri işleme prensiplerini, güvenlik tedbirlerini ve gizlilik standartlarını düzenleyen Türkçe politika metnidir. Son güncelleme: 11 Eylül 2026.

## 1. Giriş

Bu Gizlilik Politikası, Geliştiricinin Vancrone Android uygulamasıyla bağlantılı olarak bilgileri nasıl ele aldığını açıklar. Bu politikayı temel bir ilke üzerine kurduk: Biz, yani Geliştirici, kişisel envanterinizi, garanti belgelerinizi, faturalarınızı veya fotoğraflarınızı görmüyoruz ve toplamıyoruz. Bu politika, bu durumun tam olarak ne anlama geldiğini ve üçüncü taraf hizmet sağlayıcılarımızın topladığı sınırlı teknik verileri açıklar.

Sorumluluk Kimde: Vancrone, bu politikada "Geliştirici" olarak anılan bağımsız bir bireysel geliştirici tarafından yayımlanır. Geliştiriciye vancrone.app@gmail.com adresinden ulaşabilirsiniz; Google tarafından doğrulanan yayıncı bilgileri Google Play mağaza sayfasında gösterilmektedir. Garanti kayıtlarınız, faturalarınız ve fotoğraflarınız münhasıran kendi cihazınızın yerel depolama alanında saklandığından, Geliştirici bu içeriği hiçbir zaman uzaktan almaz ve bu içerik bakımından veri sorumlusu olarak hareket etmez. Geliştirici yalnızca 6. ve 14. bölümlerde açıklanan sınırlı tanılama, anonim çökme raporları, reklam sunumu ve satın alma doğrulama verileri bakımından veri sorumlusudur.

## 2. Yaklaşımımız: Tasarımı Gereği Önce Yerel (Offline-First)

Vancrone, "önce çevrimdışı" (offline-first) bir mimari üzerine kurulmuştur. Uygulamaya girdiğiniz ürün bilgilerini, seri numaralarını, fiyatları, tarihleri, notları, fatura fotoğraflarını veya kasa kanıt videolarını saklayan, dizinleyen ya da bunlara erişebilen merkezî bir Vancrone sunucusu yoktur. Bu durum bilinçli bir mimari tercihtir ("tasarımı gereği gizlilik").

## 3. Toplamadığımız Veriler

Aşağıdakileri kesinlikle toplamıyor, iletmiyor, görüntülemiyor, satmıyor, kiralamıyor veya bunlara erişmiyoruz:

- Ürün envanteri ve garanti kayıtlarınız (adlar, fiyatlar, tarihler, seri numaraları, notlar);
- Fatura, fiş fotoğraflarınız veya kasa kanıt videolarınız;
- Uygulamanın sizin için yerel olarak oluşturduğu finansal risk ve garanti durum özetleri.

Bu veriler tamamen sizin tarafınızdan oluşturulur ve siz bunları kendiniz dışa aktarana kadar yalnızca cihazınızın yerel belleğinde kalır.

## 4. Cihazınızda Yerel Olarak Saklanan Veriler

Tüm Kullanıcı İçeriği, cihazınızdaki yerel bir veritabanında saklanır ve AES-256 şifrelemesiyle korunur; bu koruma veritabanı için SQLCipher, hassas yapılandırma ve tercihler için ise Android'in donanım destekli EncryptedSharedPreferences bileşeni aracılığıyla sağlanır. AES-256, hassas verileri korumak için finans kuruluşları ve küresel güvenlik standartları tarafından kabul gören en yüksek şifreleme seviyelerinden biridir.

## 5. Storage Access Framework (SAF) ile Şifreli Manuel Yedekleme

Vancrone herhangi bir Google Drive API senkronizasyonu veya merkezi bulut yedekleme sunucusu barındırmaz. Bunun yerine, verilerinizi güvenle yedekleyebilmeniz için Android'in modern Storage Access Framework (SAF) altyapısını kullanır:

- Manuel Dışa Aktarma: Ayarlar menüsünden "Yedekle (Dışa Aktar)" seçeneğini kullandığınızda; yerel veritabanınız, kasa dosyalarınız ve fatura görselleriniz tek bir arşivde toplanır ve cihazınızın donanım anahtarlarıyla AES-256-GCM standardında şifrelenerek tek bir dosya (.vcb) haline getirilir.
- Tam Kullanıcı Denetimi: Bu dosya yalnızca sizin SAF iletişim penceresinde belirlediğiniz konuma (cihaz hafızası, SD kart, USB bellek veya bilgisayarınız) kaydedilir.
- Geliştiricinin Erişimi Yoktur: Bu şifreli yedek dosyası Geliştiricinin veya herhangi bir üçüncü tarafın sunucusuna iletilmez. Yedeğin saklanması, harici ortamlara aktarılması ve korunması tamamen kullanıcının sorumluluğundadır.

## 6. Vancrone'un Kullandığı Üçüncü Taraf Hizmetler

Vancrone, çalışabilmek için Google tarafından sağlanan sınırlı sayıda resmi SDK'ya dayanır:

- Google Firebase Crashlytics — Çökme Raporlama: Uygulama kararlılığını sağlamak ve yazılım hatalarını giderebilmek amacıyla anonim çökme günlükleri Firebase Crashlytics tarafından işlenir.
- Google AdMob — Reklam (Ücretsiz Sürüm): Vancrone'un ücretsiz sürümünde banner ve ödüllü reklamları sunmak ve ölçümlemek amacıyla Google AdMob kullanılır.
- Google ML Kit — Cihaz Üzerinde Fatura Tarama (OCR): Fatura tarayıcısı, Google ML Kit'in tamamen cihaz üzerinde (on-device) çalışan metin tanıma modülünü kullanır. Taranan görseller ve metinler cihazınızdan hiçbir yere yüklenmez.
- Google Play Faturalandırma — Satın Alımlar: Pro ve Business yükseltmeleri Google Play Faturalandırma aracılığıyla doğrulanır; ödeme bilgileri doğrudan Google tarafından işlenir.

## 7. Sunucu Tarafı Altyapı Yok

Vancrone herhangi bir merkezi sunucu işletmez. Geliştirici; envanter verileriniz, lisanslarınız veya yedekleriniz için hiçbir uzak arka uç (backend) hizmeti çalıştırmaz. 6. bölümde belirtilen Google SDK tanılamaları dışında cihazınızdan Geliştiriciye ait herhangi bir sunucuya hiçbir veri çıkışı gerçekleşmez.

## 8. Güvenlik Önlemleri

Yerel AES-256 şifrelemesinin yanı sıra; SQL enjeksiyonlarına karşı koruma, yüklenen dosyaların yerel OCR motoruna girmeden önce taranması ve sahte lisanslamayı önlemek adına Google Play kriptografik imza doğrulamaları uygulanmaktadır. Hiçbir dijital güvenlik tedbiri mutlak koruma sağlayamayacağından, cihaz güvenliğinizi sağlamak sizin sorumluluğunuzdadır.

## 9. Veri Saklama ve Kontrolünüz

Verileriniz cihazınızda bulunduğu için tüm kontrol sizdedir:

- Uygulama içi "Tüm Verileri Sıfırla": Yerel şifreli veritabanınızı, kasa kanıtlarınızı ve görsellerinizi kalıcı ve geri döndürülemez biçimde yok eder.
- Uygulamayı kaldırmak: Cihaz işletim sistemi tarafından uygulamanın tüm yerel verilerinin kalıcı olarak silinmesini sağlar.
- Geliştirici hiçbir zaman bu verilerin kopyasına sahip olmadığından, silinen verilerin kurtarılması mümkün değildir.

## 10. Çocukların Gizliliği

Vancrone 13 yaşından küçük çocuklara yönelik değildir ve çocuklardan bilerek kişisel veri toplanmaz.

## 11. Kullanıcı Seçenekleri

- Reklamlar: Android cihaz ayarlarından (Google > Reklamlar) reklam kişiselleştirmesini kapatabilir veya Reklam Kimliğinizi sıfırlayabilirsiniz. Dilerseniz Pro/Business sürümüne geçerek reklamları tamamen kaldırabilirsiniz.
- Yedekleme: Ayarlar menüsünden dilediğiniz zaman Storage Access Framework (SAF) ile şifreli yedek (.vcb) alabilir veya mevcut yedeğinizi geri yükleyebilirsiniz.
- Tanılama: Cihaz düzeyinde anonim kullanım/hata raporlamasını Android ayarlarınızdan kısıtlayabilirsiniz.
- Veri İmhası: Dilediğiniz an Ayarlar > "Tüm Verileri Sıfırla" adımıyla verilerinizi sıfırlayabilirsiniz.

## 12. Uluslararası Veri Aktarımları

Entegre Google SDK'ları küresel ölçekte çalıştığından, 6. bölümde sayılan sınırlı tanılama ve reklam verileri Google tarafından Amerika Birleşik Devletleri dâhil olmak üzere kendi ülkenizin dışında işlenebilir.

## 13. Gizlilik Haklarınız

Yürürlükteki veri koruma mevzuatları (KVKK, GDPR vb.) kapsamında; teknik verilere ilişkin bilgi talep etme hakkınız bulunmaktadır. Kullanıcı İçeriğiniz ise doğrudan sizin cihazınızda bulunduğundan, bu verilere erişim, düzeltme ve silme haklarını doğrudan uygulama üzerinden kendiniz kullanabilirsiniz.

## 14. Bölgeye Özgü Gizlilik Bilgileri

- Avrupa Ekonomik Alanı, Birleşik Krallık ve İsviçre: Tanılama verileri için meşru menfaat, kişiselleştirilmiş reklam için açık rıza, satın alımlar için sözleşmenin ifası hukuki sebeplerine dayanılır. Yerel veri koruma otoritenize başvurma hakkınız saklıdır.
- Amerika Birleşik Devletleri: Geliştirici, California Tüketici Gizliliği Yasası (CCPA) kapsamında kişisel bilgileri satmaz veya paylaşmaz.
- Japonya: Kişisel Bilgilerin Korunması Kanunu (APPI) kapsamındaki haklarınız saklıdır.
- Türkiye: 6698 sayılı KVKK kapsamındaki haklarınız saklıdır; veri sorumlusu sıfatıyla Geliştiriciye vancrone.app@gmail.com adresinden ulaşabilirsiniz.

Geliştirici bağımsız bir bireysel geliştirici olduğundan, e-postalara makul bir süre içinde ve geliştirme olanakları çerçevesinde yanıt verilmektedir.