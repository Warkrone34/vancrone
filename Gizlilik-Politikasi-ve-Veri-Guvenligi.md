# Gizlilik Politikası ve Veri Güvenliği

> Bu belge, İngilizce esas sürümün eksiksiz Türkçe çevirisidir ve aynı anlamı taşır. Son güncelleme: 11 Eylül 2026.

## 1. Giriş

Bu Gizlilik Politikası, Geliştiricinin Vancrone Android uygulamasıyla bağlantılı olarak bilgileri nasıl ele aldığını açıklar. Bu politikayı tek bir temel gerçeğin üzerine kurduk: Biz, yani Geliştirici, kişisel envanterinizi, faturalarınızı veya fotoğraflarınızı görmüyoruz. Bu politika, bunun tam olarak ne anlama geldiğini ve üçüncü taraf hizmet sağlayıcılarımızın topladığı sınırlı verinin neler olduğunu açıklar.

Sorumluluk kimde: Vancrone, bu politikada Geliştirici olarak anılan bağımsız bir geliştirici tarafından geliştirilir ve yayımlanır. Geliştiriciye vancrone.app@gmail.com adresinden ulaşabilirsiniz; Google tarafından doğrulanan yayıncı bilgileri, Google Play'deki Vancrone sayfasında gösterilir. Garanti kayıtlarınız, faturalarınız ve fotoğraflarınız kendi cihazınızda ve yedeklemeyi açmanız hâlinde kendi Google Drive hesabınızın içinde kaldığından, Geliştirici bu içeriği hiçbir zaman almaz ve bu içerik bakımından veri sorumlusu olarak hareket etmez. Geliştirici yalnızca 6. ve 14. bölümlerde açıklanan sınırlı tanılama, reklam ve satın alma doğrulama verileri bakımından veri sorumlusudur.

## 2. Yaklaşımımız: Tasarımı Gereği Önce Yerel

Vancrone, "önce çevrimdışı" (offline-first) bir mimari üzerine kurulmuştur. Uygulamaya girdiğiniz ürün bilgilerini, fiyatları, tarihleri, notları, fatura fotoğraflarını veya kanıt videolarını saklayan, dizinleyen ya da bunlara erişebilen merkezî bir Vancrone sunucusu yoktur. Bu, yalnızca bir politika taahhüdü değil; bazen "tasarımı gereği gizlilik" olarak adlandırılan, bilinçli bir mimari tercihtir.

## 3. Toplamadığımız Veriler

Aşağıdakileri toplamıyor, iletmiyor, görüntülemiyor, satmıyor, kiralamıyor veya başka bir şekilde bunlara erişmiyoruz:

- Ürün envanteri kayıtlarınız (adlar, fiyatlar, tarihler, garanti koşulları, notlar);
- Fatura veya fiş fotoğraflarınız ile kanıt videolarınız;
- Uygulamanın sizin için oluşturduğu finansal risk özetleri.

Bu veriler sizin tarafınızdan oluşturulur ve cihazınızda kalır — tercih etmeniz hâlinde kendi kişisel Google Drive hesabınızda da bulunur — siz bunları kendiniz paylaşmaya veya dışa aktarmaya karar verene kadar.

## 4. Cihazınızda Yerel Olarak Saklanan Veriler

Tüm Kullanıcı İçeriği, cihazınızdaki yerel bir veritabanında saklanır ve AES-256 şifrelemesiyle korunur; bu, veritabanı için SQLCipher, daha küçük yapılandırma ve tercih verileri için Android'in EncryptedSharedPreferences bileşeni aracılığıyla uygulanır. AES-256, hassas bilgileri korumak için finans kuruluşları ve devlet sistemleri tarafından da yaygın biçimde kullanılan şifreleme standardıdır.

## 5. Kendi Google Drive Hesabınız Üzerinden İsteğe Bağlı Bulut Yedeği

Vancrone, açmanız hâlinde verilerinizi şifreleyerek Google'ın kısıtlı appDataFolder kapsamını kullanarak kendi kişisel Google Drive hesabınıza eşitleyen isteğe bağlı bir yedekleme özelliği sunar. Bu, uygulamada şu anlama gelir:

- Yedeğiniz, özel olarak Vancrone'a bağlı, gizli bir uygulama verisi klasöründe bulunur — olağan Google Drive dosya listenizde görünmez ve diğer uygulamalar bunu göremez.
- Eşitleme doğrudan cihazınız ile Google hesabınız arasında gerçekleşir; Geliştirici arada bir sunucu işletmez ve bu yedek verilerine erişimi yoktur.
- Yedeğiniz, Google hesabınıza ve Google'ın kendi Gizlilik Politikası ile Hizmet Şartlarına tabidir.
- Bu özelliği kapatırsanız, yedeği Google hesabınızdan silerseniz veya Google hesap izinlerinizden Vancrone'un Drive erişimini geri alırsanız, yedek buna uygun olarak kaldırılır.

## 6. Vancrone'un Kullandığı Üçüncü Taraf Hizmetler

Vancrone'un envanter verileriniz için merkezî bir sunucusu olmamasına karşın, çalışabilmek için az sayıda Google hizmetine dayanır ve bunların her biri kendi sınırlı verisini oluşturur:

- Google Firebase Crashlytics — Çökme Raporlama: Uygulamanın ne zaman ve neden çöktüğünü anlayıp hataları giderebilmek için Firebase Crashlytics'i kullanıyoruz.
- Google AdMob — Reklam (Ücretsiz Sürüm): Vancrone'un ücretsiz sürümünü kullanıyorsanız, banner ve ödüllü reklamları göstermek için Google AdMob'u kullanıyoruz.
- Google ML Kit — Cihaz Üzerinde Fatura Tarama (OCR): Vancrone'un fatura tarayıcısı, Google ML Kit'in cihaz üzerinde çalışan metin tanıma özelliğini kullanır. Fatura fotoğraflarınız ve bunlardan çıkarılan metin tamamen cihazınızda işlenir; bu özellik için Google'a veya başka birine yüklenmez.
- Google Play Faturalandırma — Satın Alımlar: Pro ve Business "Ömür Boyu" yükseltmelerine ilişkin satın alımlar tamamen Google Play Faturalandırma tarafından işlenir.

## 7. Sunucu Tarafı Altyapı Yok

Vancrone herhangi bir sunucu işletmez. Geliştirici; envanter verileriniz, lisansınız veya başka bir şey için hiçbir arka uç hizmeti çalıştırmaz. Pro ve Business satın alımları, Google Play Faturalandırma aracılığıyla kendi cihazınızda doğrulanır ve hiçbir satın alma bilgisi Geliştiricinin işlettiği bir sunucuya gönderilmez. Kendi Google Drive hesabınızda saklanan isteğe bağlı yedek ile 6. bölümde açıklanan çökme tanılamaları dışında, cihazınızdan Geliştiricinin çalıştırdığı herhangi bir hizmete veri çıkmaz.

## 8. Güvenlik Önlemleri

Yukarıda açıklanan yerel AES-256 şifrelemesinin ötesinde, Vancrone'un mimarisine uygun teknik güvenlik önlemleri uyguluyoruz. Bunlar arasında; enjeksiyon türü saldırılara karşı korunmak için girdi temizleme, yüklenen veya taranan dosyaların cihaz üzerindeki OCR motoruna ulaşmadan önce doğrulanması ve sahte satın alma olaylarını engellemek için Google Play Faturalandırma'nın cihazınızda döndürdüğü satın alma verilerinin kriptografik imza doğrulaması yer alır. Hiçbir güvenlik önlemi kusursuz değildir ve mutlak güvenliği garanti edemeyiz.

## 9. Veri Saklama ve Kontrolünüz

Verileriniz cihazınızda bulunduğu için kontrol sizdedir:

- Uygulama içi "Tüm Verileri Temizle": Yerel şifreli veritabanınızı ve ilişkili medyayı kalıcı ve geri dönüşü olmayan biçimde siler.
- Uygulamayı kaldırmak: Bu verileri cihazınızdan aynı şekilde kalıcı ve geri dönüşü olmayan biçimde siler.
- Bu verilerin hiçbir yerde bir kopyasını tutmuyoruz, çünkü hiçbir zaman bir kopyamız olmadı.

## 10. Çocukların Gizliliği

Vancrone çocuklara yönelik değildir ve uygun bir onay olmaksızın çocuklardan bilerek kişisel veri toplamayız.

## 11. Seçenekleriniz

- Reklamlar: Android cihaz ayarlarınızdan reklam kişiselleştirmesini sınırlayabilir veya Reklam Kimliğinizi sıfırlayabilir; ya da Pro/Business'a yükselterek reklamları tamamen kaldırabilirsiniz.
- Bulut yedeği: Google Drive yedeklemesini Uygulamanın ayarlarından dilediğiniz zaman açıp kapatabilirsiniz.
- Tanılama: Cihazınızın veya Android sürümünüzün tanılama verisi paylaşımı için işletim sistemi düzeyinde bir kapatma seçeneği sunduğu durumlarda, bu ayara uyulur.
- Verileriniz: 9. bölümde açıklandığı şekilde dilediğiniz zaman "Tüm Verileri Temizle" seçeneğini kullanabilir veya Uygulamayı kaldırabilirsiniz.

## 12. Uluslararası Veri Aktarımları

Hizmet sağlayıcılarımız (Google) küresel ölçekte faaliyet gösterdiğinden, 6. bölümde açıklanan sınırlı verilerin bir kısmı — örneğin Crashlytics tanılamaları, AdMob reklam verileri veya Play Faturalandırma satın alma verileri — Amerika Birleşik Devletleri dâhil olmak üzere kendi ülkenizin dışında işlenebilir.

## 13. Gizlilik Haklarınız

Yaşadığınız yere bağlı olarak; bu politikada açıklanan sınırlı verilere erişme, bunları düzeltme, silme veya işlenmesini kısıtlama ve belirli işleme faaliyetlerine (örneğin reklam kişiselleştirmesine) itiraz etme haklarına sahip olabilirsiniz. Verilerinizin büyük bölümü esasen bize hiç ulaşmadığı için, bu hakların birçoğunu doğrudan Uygulama üzerinden (9. bölüm) veya Google hesap ayarlarınızdan hâlihazırda kullanabilirsiniz.

## 14. Bölgeye Özgü Gizlilik Bilgileri

- Avrupa Ekonomik Alanı, Birleşik Krallık ve İsviçre: Bu politikada açıklanan sınırlı veriler bakımından veri sorumlusu Geliştiricidir. Hukuki sebepler; çökme ve kararlılık tanılamaları için meşru menfaat, kişiselleştirilmiş reklam için onayınız ve Google Play üzerinden yaptığınız satın alımların doğrulanması için sözleşmenin ifasıdır. Erişim, düzeltme, silme, kısıtlama ve taşınabilirlik talep etme, işlemeye itiraz etme ve onayınızı dilediğiniz zaman geri alma hakkına sahipsiniz. Kişiselleştirilmiş reklam, yalnızca Uygulamada gösterilen onay talebi aracılığıyla onay vermeniz hâlinde gösterilir ve bu tercihinizi dilediğiniz zaman değiştirebilirsiniz. Geliştirici kişisel veri satmaz. Tanılama ve reklam verileri, Google'ın hizmet sağlayıcı olarak uyguladığı güvenceler kapsamında ülkenizin dışında Google tarafından işlenebilir. Ulusal denetim otoritenize şikâyette bulunabilirsiniz; örneğin Birleşik Krallık'ta Information Commissioner's Office, İsviçre'de Federal Veri Koruma ve Bilgi Komiseri.
- Japonya: Veri işleyen kuruluş, vancrone.app@gmail.com adresinden ulaşılabilen Geliştiricidir. Kullanım amaçları; çökmelerin teşhis edilmesi, Uygulamanın kararlı tutulması, reklam gösterilmesi ve satın alımların doğrulanmasıyla sınırlıdır. Kişisel bilgiler, hizmet sağlayıcı olarak Google'a sağlanabilir ve Amerika Birleşik Devletleri dâhil olmak üzere Japonya dışında işlenebilir. Kişisel bilgilerinizin açıklanmasını, düzeltilmesini veya kullanımının durdurulmasını yukarıdaki adrese yazarak talep edebilirsiniz.
- Amerika Birleşik Devletleri: Vancrone 13 yaşından küçük çocuklara yönelik değildir ve Geliştirici, 13 yaşından küçük çocuklardan bilerek kişisel bilgi toplamaz. Geliştirici, California hukukunda kullanıldığı anlamda kişisel bilgileri satmaz veya paylaşmaz. Reklam kişiselleştirmesini dilediğiniz zaman cihaz ayarlarınızdan, Google ve ardından Reklamlar bölümünden sınırlayabilirsiniz.
- Türkiye: 6698 sayılı Kanun'un (KVKK) 11. maddesi kapsamındaki haklarınız GDPR/KVKK Aydınlatma Metninde belirtilmiştir. Öncelikle Geliştirici ile iletişime geçebilir, ayrıca Kişisel Verileri Koruma Kurumu'na şikâyette bulunabilirsiniz.
- Diğer ülkeler: Brezilya, Meksika, Kanada, Avustralya, Tayvan, Hong Kong ve Singapur dâhil olmak üzere yaşadığınız ülkenin hukuku size bu politikanın ötesinde haklar tanıyorsa, o haklar geçerlidir. Geliştiriciye vancrone.app@gmail.com adresinden veya yerel makamınıza başvurabilirsiniz.
