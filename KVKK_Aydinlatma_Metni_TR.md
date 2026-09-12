# KVKK Aydınlatma Metni ve Sorumluluk Reddi

> Bu belge, Vancrone uygulamasının veri işleme prensiplerini ve sorumluluk sınırlarını düzenleyen Türkçe aydınlatma metnidir. Son güncelleme: 11 Eylül 2026.

## Bu Belgenin Amacı

Bu Aydınlatma Metni; 6698 sayılı Kişisel Verilerin Korunması Kanunu'nun ("KVKK") 10. maddesi ve uygulanabildiği ölçüde Avrupa Birliği Genel Veri Koruma Tüzüğü'nün ("GDPR") 13–14. maddeleri uyarınca, bağımsız Geliştiricinin Vancrone uygulamasıyla bağlantılı olarak kişisel verilerinizi nasıl işlediği hakkında sizi bilgilendirmek amacıyla hazırlanmıştır.

## 1. Veri Sorumlusunun Kimliği ve Sorumluluğun Kapsamı

Veri Sorumlusu: Burada "Geliştirici" olarak anılan, Vancrone uygulamasının bağımsız geliştiricisi. Google tarafından doğrulanan yayıncı bilgileri, Google Play'deki Vancrone mağaza sayfasında gösterilmektedir.

İletişim: vancrone.app@gmail.com

Sorumluluğun Kapsamı: Geliştirici, yalnızca aşağıda açıklanan sınırlı teknik tanılama, anonim çökme raporları, reklam sunumu ve mağaza içi satın alma doğrulama verileri bakımından veri sorumlusudur. Garanti kayıtlarınız, faturalarınız, kasa kayıtlarınız ve fotoğraflarınız yalnızca kendi cihazınızın yerel belleğinde saklanır; Storage Access Framework (SAF) aracılığıyla dışa aktardığınız şifreli yedekleriniz (.vcb) ise tamamen sizin belirlediğiniz dosya dizininde kalır. Geliştirici hiçbir kullanıcı hesabı, bulut veritabanı veya uzak sunucu işletmez; bu verilere hiçbir erişimi yoktur ve bu verilerin veri sorumlusu değildir.

## 2. Hangi Kişisel Verileri, Neden İşliyoruz

Vancrone'un envanter, fatura, garanti ve finansal takip verileri ("Kullanıcı İçeriği"), Uygulamanın temel işlevlerini size çevrimdışı (offline-first) olarak sunmak amacıyla cihazınızda yerel olarak işlenir. Geliştirici bu Kullanıcı İçeriğini almaz, uzaktan depolamaz ve işlemez.

Uygulamanın çalışması için kullanılan üçüncü taraf Google SDK'larına otomatik olarak aktarılan sınırlı veri kategorileri şunlardır:

- Çökme tanılamaları: Uygulama kararlılığı sorunlarını tespit etmek ve gidermek amacıyla Google (Firebase Crashlytics) tarafından anonim olarak işlenir.
- Reklam verileri: Ücretsiz sürüm kullanıcılarına reklam sunmak ve gösterim ölçümlemek amacıyla Google (AdMob) tarafından işlenir.
- Satın alma verileri: Lisans doğrulaması amacıyla Google (Play Faturalandırma) tarafından işlenir. Geliştirici bu amaçla herhangi bir sunucu işletmez ve yalnızca Google Play'in cihaza bildirdiği lisans durumunu doğrular.

## 3. Toplama Yöntemi ve Hukuki Sebep

Toplama yöntemi: Yukarıdaki veriler, Uygulamayı kullanırken Uygulamaya yerleşik Google kütüphaneleri (Firebase Crashlytics, AdMob, Google Play Faturalandırma) aracılığıyla cihazınızdan otomatik olarak toplanır.

KVKK ve GDPR kapsamındaki hukuki sebep: Çökme tanılamaları ve satın alma doğrulaması; temel hak ve özgürlüklerinize zarar vermemek kaydıyla meşru menfaat (Uygulamanın işlevsel, hatasız ve güvenli tutulması ile satın alımların yerine getirilmesi) hukuki sebebine dayanılarak işlenir. Temel düzeydeki (kişiselleştirilmemiş) reklam aynı hukuki sebebe dayanabilir; kişiselleştirilmiş reklamın gerektirdiği durumlarda Google Kullanıcı Rıza Politikası doğrultusunda açık rızanıza dayanılır.

## 4. Verilerinizin Kimlere ve Hangi Amaçla Aktarılabileceği

Verileriniz; Firebase Crashlytics, AdMob ve Google Play Faturalandırma bakımından veri işleyen konumunda olan Google Ireland Limited / Google LLC ile bunların bağlı şirketlerine aktarılabilir. Uygulama herhangi bir Google Drive API veya harici bulut sunucusu aktarımı yapmaz. Kişisel verilerinizi üçüncü kişilere satmıyoruz ve Kullanıcı İçeriğinizi hiç kimseye aktarmıyoruz — çünkü bu veriler cihazınızdan asla dışarı çıkmaz.

## 5. Sınır Ötesi Veri Aktarımları

4. bölümde sayılan alıcılar (özellikle Google altyapısı), teknik tanılama ve reklam verilerini Türkiye ve/veya Avrupa Ekonomik Alanı dışında, Amerika Birleşik Devletleri dâhil olmak üzere işleyebilir. Bu tür aktarımlar; Google tarafından uygulanan standart sözleşme hükümleri (SCC), yeterlilik kararları veya KVKK/GDPR kapsamında kabul edilen uluslararası aktarım mekanizmalarına dayanılarak yürütülür.

## 6. Saklama Süresi

- Cihazınızda yerel olarak saklanan Kullanıcı İçeriğiniz; siz silene, Ayarlar menüsünden "Tüm Verileri Sıfırla" seçeneğini kullanana veya Uygulamayı cihazınızdan kaldırana kadar saklanır.
- Çökme tanılamaları, Google/Firebase tarafından standart Crashlytics saklama politikaları uyarınca saklanır.
- Reklam verileri, Google tarafından kendi reklam veri saklama uygulamaları uyarınca saklanır.
- Satın alma/lisans verileri, Google Play hesabınız üzerinden Google tarafından yönetilir ve lisansınızı desteklemek için gerekli olduğu sürece saklanır.

## 7. Haklarınız ve Doğrudan Kontrol

KVKK (11. madde) ve GDPR (15-21. maddeler) uyarınca ilgili kişi olarak; kişisel verilerinizin işlenip işlenmediğini öğrenme, bilgi talep etme, düzeltilmesini veya silinmesini isteme haklarına sahipsiniz.

ÖNEMLİ NOT: Vancrone merkezi bir veritabanı veya kullanıcı hesabı tutmadığı için, Kullanıcı İçeriğinize (envanter, fatura ve görseller) dair tüm kontrol ve silme yetkisi doğrudan sizin elinizdedir. Uygulama içerisinden kayıtlarınızı dilediğiniz an tek tek silebilir veya Ayarlar > "Tüm Verileri Sıfırla" adımıyla tüm verilerinizi kalıcı olarak yok edebilirsiniz. Reklam kimliğinizi ise Android Cihaz Ayarları > Google > Reklamlar menüsünden dilediğiniz an sıfırlayabilirsiniz.

## 8. Haklarınızı Nasıl Kullanabilirsiniz ve Yanıt Süreçleri

Vancrone, kurumsal bir çağrı merkezi veya tam zamanlı bir müşteri destek birimi bulunmayan bağımsız bir bireysel geliştirici tarafından geliştirilmekte ve sürdürülmektedir.

Yukarıda belirtilen haklarınız kapsamındaki sorularınız için vancrone.app@gmail.com adresine yazabilirsiniz. Geliştirici, Kullanıcı İçeriği verilerinize teknik olarak sahip olmadığından ve bunları uzaktan göremediğinden, içerik silme veya yedek kurtarma taleplerini uzaktan yerine getiremez. Geliştirici, geliştirme döngüleri, kişisel uygunluk ve teknik imkânlar dâhilinde gelen e-postalara makul bir süre içinde yanıt vermeyi amaçlar; ancak tam zamanlı bir destek ekibi bulunmadığından yanıt sürelerinde gecikmeler yaşanabileceğini lütfen göz önünde bulundurunuz.

## 9. "Aydınlatma" ile "Açık Rıza" Arasındaki Ayrım Üzerine Not

Bu Aydınlatma Metni, verilerinizin nasıl işlendiği konusunda sizi bilgilendirme yükümlülüğümüzü yerine getirir — kendisi tek başına bir rıza beyanı değildir. Ayrı ve açık rızanıza ihtiyaç duyulan durumlarda (örneğin kişiselleştirilmiş reklam tercihlerinizde) bu onay Uygulama başlangıcındaki onay pencereleri aracılığıyla bağımsız olarak talep edilir.

## 10. Bölgeye Göre Şikâyet Mercileri

Haklarınız konusunda yerel düzenleyici denetim kurumlarına başvurma hakkınız saklıdır:

- Türkiye: Kişisel Verileri Koruma Kurumu (KVKK Kurumu).
- Avrupa Ekonomik Alanı (AEA): Yaşadığınız AB üye ülkesinin yetkili veri koruma kurumu (DPA).
- Birleşik Krallık: Information Commissioner's Office (ICO).
- İsviçre: Federal Veri Koruma ve Bilgi Komiseri (FDPIC).
- Japonya: Kişisel Bilgilerin Korunması Komisyonu (PPC).
- Diğer ülkeler: İlgili yerel tüketici hakları veya veri koruma kurumunuz.

Her durumda öncelikle vancrone.app@gmail.com adresine yazarak bilgi alabilirsiniz.