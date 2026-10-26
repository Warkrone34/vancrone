# KVKK Aydınlatma Metni ve Sorumluluk Reddi

> Bu belge, Vancrone uygulamasının veri işleme prensiplerini ve sorumluluk sınırlarını düzenleyen Türkçe aydınlatma metnidir. Son güncelleme: 15 Ekim 2026.

## Bu Belgenin Amacı

Bu Aydınlatma Metni; 6698 sayılı Kişisel Verilerin Korunması Kanunu'nun ("KVKK") 10. maddesi ve uygulanabildiği ölçüde Avrupa Birliği Genel Veri Koruma Tüzüğü'nün ("GDPR") 13–14. maddeleri uyarınca, bağımsız Geliştiricinin Vancrone uygulamasıyla bağlantılı olarak kişisel verilerinizi nasıl işlediği hakkında sizi bilgilendirmek amacıyla hazırlanmıştır.

## 1. Veri Sorumlusunun Kimliği ve Sorumluluğun Kapsamı

Veri Sorumlusu: Burada "Geliştirici" olarak anılan, Vancrone uygulamasının bağımsız geliştiricisi. Google tarafından doğrulanan yayıncı bilgileri, Google Play'deki Vancrone mağaza sayfasında gösterilmektedir.

İletişim: vancrone.app@gmail.com

Sorumluluğun Kapsamı: Geliştirici, yalnızca aşağıda açıklanan sınırlı veriler bakımından veri sorumlusudur: çökme raporları, uygulama içi satın alma kayıtları (satın alma sunulursa) ve uygulama içi geri bildirim formuyla gönderdiğiniz mesajlar. Garanti kayıtlarınız, faturalarınız, kasa kayıtlarınız ve fotoğraflarınız yalnızca kendi cihazınızın yerel belleğinde saklanır; Storage Access Framework (SAF) aracılığıyla dışa aktardığınız şifreli yedekleriniz (.vcb) ise tamamen sizin belirlediğiniz dosya dizininde kalır. Geliştirici bu içerik için hiçbir kullanıcı hesabı, bulut veritabanı veya uzak sunucu işletmez; bu verilere hiçbir erişimi yoktur ve bu verilerin veri sorumlusu değildir.

## 2. Hangi Kişisel Verileri, Neden İşliyoruz

Vancrone'un envanter, fatura, garanti ve finansal takip verileri ("Kullanıcı İçeriği"), Uygulamanın temel işlevlerini size çevrimdışı (offline-first) olarak sunmak amacıyla cihazınızda yerel olarak işlenir. Geliştirici bu Kullanıcı İçeriğini almaz, uzaktan depolamaz ve işlemez.

Uygulamayla bağlantılı olarak işlenen sınırlı veri kategorileri şunlardır:

- Çökme tanılamaları (Google Firebase Crashlytics): Hata yığını, cihaz modeli, Android sürümü, uygulama sürümü, rastgele bir kurulum kimliği ve hatanın zamanı; uygulama kararlılığı sorunlarını tespit etmek ve gidermek amacıyla işlenir. Bu veriler takma adlıdır (pseudonymous): adınızla veya e-posta adresinizle ilişkilendirilmez ve Kullanıcı İçeriği barındırmaz.
- Satın alma ve lisans verileri (Google Play Faturalandırma): Mevcut sürüm uygulama içi satın alma sunmaz ve Google Play Faturalandırma'ya bağlanmaz; bu nedenle satın alma verisi işlenmez. İsteğe bağlı Pro/Business yükseltmeleri sunulursa, satın aldığınız özellikleri sunmak amacıyla sipariş ve satın alma durumu bilgileri işlenir; ödeme bilgileri yalnızca Google tarafından işlenir ve bu Aydınlatma Metni önceden güncellenir.
- Geri bildirim mesajları (yalnızca siz gönderdiğinizde): Mesajınız, gönderdiğiniz e-posta adresi, cihaz üreticisi ve modeli, Android sürümü, uygulama sürümü ve gönderim zamanı; size yanıt vermek ve bildirilen sorunu gidermek amacıyla işlenir.

Uygulamanın mevcut sürümü reklam göstermez ve Google AdMob SDK'sını içermez. Reklam eklenirse bu Aydınlatma Metni ilgili sürümden önce güncellenecektir.

## 3. Toplama Yöntemi ve Hukuki Sebep

Toplama yöntemi: Çökme raporları, Uygulamayı kullanırken Uygulamaya yerleşik Firebase Crashlytics kütüphanesi aracılığıyla cihazınızdan otomatik yollarla toplanır (satın alma sunulursa satın alma verileri Google Play Faturalandırma aracılığıyla toplanır). Geri bildirim mesajları yalnızca, kendi e-posta uygulamanızdan Geliştiricinin adresine (vancrone.app@gmail.com) e-posta göndermeyi seçtiğinizde alınır; Uygulama bu mesajları kendisi iletmez.

KVKK ve GDPR kapsamındaki hukuki sebep: Çökme tanılamaları, temel hak ve özgürlüklerinize zarar vermemek kaydıyla meşru menfaat (Uygulamanın işlevsel, hatasız ve güvenli tutulması) hukuki sebebine dayanılarak işlenir. Satın alma verileri sözleşmenin kurulması ve ifası (satın alınan dijital özelliklerin sunulması) hukuki sebebine dayanır. Geri bildirim mesajları, sizin başlattığınız talebin yanıtlanmasına yönelik meşru menfaate dayanılarak işlenir. İleride kişiselleştirilmiş reklam eklenirse açık rızanıza dayanılacaktır.

## 4. Verilerinizin Kimlere ve Hangi Amaçla Aktarılabileceği

Verileriniz; Firebase Crashlytics, Google Play Faturalandırma ve Geliştiricinin destek posta kutusunu barındıran Gmail bakımından veri işleyen konumunda olan Google Ireland Limited / Google LLC ile bunların bağlı şirketlerine aktarılabilir. Uygulama herhangi bir Google Drive API senkronizasyonu yapmaz ve Kullanıcı İçeriğinizi hiçbir sunucuya göndermez. Kişisel verilerinizi üçüncü kişilere satmıyoruz ve Kullanıcı İçeriğinizi hiç kimseye aktarmıyoruz — çünkü bu veriler cihazınızdan asla dışarı çıkmaz.

## 5. Sınır Ötesi Veri Aktarımları

4. bölümde sayılan alıcılar (özellikle Google altyapısı); çökme, satın alma ve geri bildirim verilerini Türkiye ve/veya Avrupa Ekonomik Alanı dışında, Amerika Birleşik Devletleri dâhil olmak üzere işleyebilir. Bu tür aktarımlar; standart sözleşmeler (SCC), yeterlilik kararları, uygulanabildiği durumlarda AB-ABD Veri Gizliliği Çerçevesi veya KVKK'nın 9. maddesi ve GDPR'ın V. Bölümü kapsamında kabul edilen diğer aktarım mekanizmalarına dayanılarak yürütülür.

## 6. Saklama Süresi

- Cihazınızda yerel olarak saklanan Kullanıcı İçeriğiniz; siz silene, Ayarlar menüsünden "Tüm Verileri Sıfırla" seçeneğini kullanana veya Uygulamayı cihazınızdan kaldırana kadar saklanır.
- Çökme tanılamaları Firebase Crashlytics tarafından 90 gün saklanır.
- Satın alma/lisans verileri, Google Play hesabınız üzerinden Google tarafından yönetilir ve lisansınızı desteklemek için gerekli olduğu sürece saklanır.
- Geri bildirim mesajları yalnızca size yanıt vermek ve bildirilen sorunu çözmek için gerekli olduğu süre boyunca saklanır.

## 7. Haklarınız ve Doğrudan Kontrol

KVKK (11. madde) ve GDPR (15-21. maddeler) uyarınca ilgili kişi olarak; kişisel verilerinizin işlenip işlenmediğini öğrenme, bilgi talep etme, düzeltilmesini veya silinmesini isteme ve meşru menfaate dayalı işlemeye itiraz etme haklarına sahipsiniz.

ÖNEMLİ NOT: Vancrone merkezi bir veritabanı veya kullanıcı hesabı tutmadığı için, Kullanıcı İçeriğinize (envanter, fatura ve görseller) dair tüm kontrol ve silme yetkisi doğrudan sizin elinizdedir. Uygulama içerisinden kayıtlarınızı dilediğiniz an tek tek silebilir veya Ayarlar > "Tüm Verileri Sıfırla" adımıyla tüm garanti kayıtlarınızı, eklerini ve Termal Fiş Kurtarıcı ile kaydedilen görselleri kalıcı olarak silebilirsiniz. Çökme raporlamasını dilediğiniz an Ayarlar > Hakkında > "Çökme Raporları" anahtarından kapatabilirsiniz; bu, bu işlemeye itiraz etmenin en doğrudan yoludur. Anahtar kapalıyken çökme raporu gönderilmez ve cihazınızda bekleyen raporlar silinir; daha önce gönderilen raporlar 6. bölümdeki süre boyunca saklanır. Mevcut sürüm Reklam Kimliğinizi toplamaz.

## 8. Haklarınızı Nasıl Kullanabilirsiniz ve Yanıt Süreçleri

Vancrone, kurumsal bir çağrı merkezi veya tam zamanlı bir müşteri destek birimi bulunmayan bağımsız bir bireysel geliştirici tarafından geliştirilmekte ve sürdürülmektedir.

Yukarıda belirtilen haklarınız kapsamındaki sorularınız için vancrone.app@gmail.com adresine yazabilirsiniz. Geliştirici, Kullanıcı İçeriği verilerinize teknik olarak sahip olmadığından ve bunları uzaktan göremediğinden, içerik silme veya yedek kurtarma taleplerini uzaktan yerine getiremez. Çökme raporları takma adlı olduğundan, Geliştirici hangi kayıtların size ait olduğunu belirleyemeyebilir. Geliştirici, geliştirme döngüleri, kişisel uygunluk ve teknik imkânlar dâhilinde gelen e-postalara makul bir süre içinde yanıt vermeyi amaçlar; ancak tam zamanlı bir destek ekibi bulunmadığından yanıt sürelerinde gecikmeler yaşanabileceğini lütfen göz önünde bulundurunuz.

## 9. "Aydınlatma" ile "Açık Rıza" Arasındaki Ayrım Üzerine Not

Bu Aydınlatma Metni, verilerinizin nasıl işlendiği konusunda sizi bilgilendirme yükümlülüğümüzü yerine getirir — kendisi tek başına bir rıza beyanı değildir. Uygulamanın mevcut sürümü açık rızaya dayalı bir veri işleme yapmamaktadır. Açık rızanızı gerektiren bir işleme (örneğin kişiselleştirilmiş reklam) eklenirse, bu onay söz konusu işleme başlamadan önce Uygulama içinde ayrıca talep edilecektir.

## 10. Bölgeye Göre Şikâyet Mercileri

Haklarınız konusunda yerel düzenleyici denetim kurumlarına başvurma hakkınız saklıdır:

- Türkiye: Kişisel Verileri Koruma Kurumu (KVKK Kurumu).
- Avrupa Ekonomik Alanı (AEA): Yaşadığınız AB üye ülkesinin yetkili veri koruma kurumu (DPA).
- Birleşik Krallık: Information Commissioner's Office (ICO).
- İsviçre: Federal Veri Koruma ve Bilgi Komiseri (FDPIC).
- Japonya: Kişisel Bilgilerin Korunması Komisyonu (PPC).
- Diğer ülkeler: İlgili yerel tüketici hakları veya veri koruma kurumunuz.

Her durumda öncelikle vancrone.app@gmail.com adresine yazarak bilgi alabilirsiniz.
