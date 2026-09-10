# Vancrone Gizlilik Politikası

Son güncelleme: 10 Eylül 2026

## 1. Kısa özet

Vancrone, garanti ve fatura kayıtlarınızı düzenli tutmanız için yapılmış bir Android uygulamasıdır.

- Girdiğiniz tüm kayıtlar, fotoğraflar ve videolar cihazınızda şifreli olarak saklanır.
- Bizim bir sunucumuz yoktur. Kayıtlarınız bize gönderilmez, geliştirici içeriğinizi göremez.
- Bulut yedeği yalnızca siz Google hesabınızı bağlarsanız çalışır. Yedek, sizin kendi Google Drive alanınıza şifrelenmiş tek bir dosya olarak yüklenir.
- Yedeği istediğiniz zaman kapatabilir ve silebilirsiniz.

## 2. Veri sorumlusu ve iletişim

Uygulama, Vancrone adıyla bağımsız bir geliştirici tarafından yayınlanmaktadır.

Sorularınız ve talepleriniz için: randomizetrust43@gmail.com

## 3. İşlenen veriler

### 3.1. Sizin girdiğiniz kayıtlar

- Ürün adı, kategori, marka veya satıcı bilgisi
- Fiyat ve para birimi
- Satın alma tarihi, garanti bitiş tarihi, hatırlatma tarihleri
- Notlar, servis ve tamir geçmişi kayıtları

### 3.2. Görseller ve videolar

- Fatura fotoğrafı, garanti belgesi görseli, ürün görseli
- Kanıt videosu (kamerayla çekip eklediyseniz)

### 3.3. İsteğe bağlı konum

Bir kayda satın alma konumu eklemeyi seçerseniz, yaklaşık konum koordinatı metin olarak kaydınıza yazılır. Konum sürekli izlenmez, arka planda toplanmaz, yalnızca o an ve yalnızca sizin isteğinizle alınır.

### 3.4. Google hesabı bilgisi

Bulut yedeğini açarsanız, Google ile giriş sırasında hesap adınız ve e-posta adresiniz uygulamaya iletilir. Uygulama yalnızca uygulamaya ait özel Drive alanına erişim izni ister. Drive'daki diğer dosyalarınızı göremez, listeleyemez ve okuyamaz.

### 3.5. Teknik veriler

- Çökme ve hata kayıtları (Firebase Crashlytics)
- İsimsiz kullanım olayları, örneğin hangi ekranın açıldığı (Firebase Analytics)
- Reklam kimliği (yalnızca reklam gösterilen sürümde, Google AdMob)
- Satın alma doğrulaması (Google Play Faturalandırma)

Bu teknik veriler kayıtlarınızın içeriğini, fotoğraflarınızı, videolarınızı, fiyatlarınızı veya notlarınızı içermez.

## 4. Verileriniz nerede saklanır

### 4.1. Cihazınızda

Kayıtlar, SQLCipher ile şifrelenmiş bir veritabanında tutulur. Şifreleme anahtarı cihazın donanım destekli Android Keystore alanında üretilir ve orada kalır. Fotoğraf ve videolar uygulamaya özel klasörde saklanır; başka uygulamalar bu klasörü okuyamaz.

### 4.2. Kendi Google Drive alanınızda

Bulut yedeğini açarsanız:

- Kayıtlarınız ve medya dosyalarınız tek bir arşiv haline getirilir.
- Arşiv, cihazda AES-256-GCM ile şifrelenir. Yükleme yalnızca şifreleme tamamlandıktan sonra yapılır.
- Şifreli arşiv, Drive'ın uygulama verileri alanına yüklenir. Bu alan Drive dosya listenizde görünmez ve başka uygulamalar tarafından okunamaz.
- Şifre çözme anahtarı cihazınızda saklanır; ayrıca Google Play Hizmetleri Block Store üzerinde ve aynı özel Drive alanında sarmalanmış olarak yedeklenir. Böylece uygulamayı silip aynı hesapla tekrar kurduğunuzda kayıtlarınız fotoğraf ve videolarıyla geri gelir.
- Yedek dosyası, indirildikten sonra bütünlük etiketiyle doğrulanır. Dosya değiştirilmişse geri yükleme reddedilir.

### 4.3. Bizde

Hiçbir yerde. Kendi sunucumuz, veri tabanımız veya arşivimiz yoktur.

## 5. İzinler ve nedenleri

- Kamera: fatura, belge ve ürün fotoğrafı çekmek, kanıt videosu kaydetmek
- Mikrofon: yalnızca video kaydı sırasında ses için
- Bildirimler: yaklaşan garanti bitiş tarihleri için hatırlatma
- Konum: yalnızca siz bir kayda satın alma konumu eklemek istediğinizde
- Fotoğraf seçimi: galeriden fatura veya ürün görseli eklemek
- İnternet: bulut yedeği, reklam gösterimi ve hata bildirimi

İzinlerin tümü isteğe bağlıdır. Vermezseniz ilgili özellik çalışmaz, uygulamanın geri kalanı çalışmaya devam eder.

## 6. Kullanılan üçüncü taraf hizmetler

- Google Drive: şifreli yedeğin sizin hesabınızda saklanması
- Google Play Hizmetleri ve Block Store: hesap bağlantısı ve anahtar yedeği
- Firebase Crashlytics ve Analytics: çökme ve isimsiz kullanım istatistikleri
- Google AdMob: reklam gösterilen sürümde reklamlar
- Google Play Faturalandırma: ücretli özellik satın alımları. Kart ve ödeme bilgileriniz Google tarafından işlenir, uygulamaya iletilmez.
- Google ML Kit ve CameraX: metin okuma, barkod ve belge tarama. Bu işlemler cihaz içinde yapılır, görüntüler bu iş için sunucuya gönderilmez.

Bu hizmetler Google tarafından sağlanır ve Google'ın kendi gizlilik koşullarına tabidir.

## 7. Saklama ve silme

- Bir kaydı sildiğinizde kayıt önce çöp kutusuna gider, oradan kalıcı olarak silebilirsiniz.
- Bulut yedeğini uygulama ayarlarından kapatabilir ve Drive'daki yedeği silebilirsiniz.
- Uygulamayı kaldırdığınızda cihazdaki tüm kayıtlar ve medya dosyaları silinir.
- Drive'daki uygulama verisini dilediğiniz zaman drive.google.com üzerinden Ayarlar bölümündeki uygulamaları yönetme ekranından da kaldırabilirsiniz.
- Kayıtlarınızı biz saklamadığımız için silme işleminden sonra bizde hiçbir kopya kalmaz.

## 8. Haklarınız

KVKK ve GDPR kapsamında verilerinize erişme, düzeltme, silme, işlemeyi kısıtlama ve itiraz etme haklarına sahipsiniz. Kayıtlarınız yalnızca cihazınızda ve sizin Drive alanınızda olduğu için bu hakların tamamını uygulama içinden doğrudan kullanabilirsiniz. Yine de bir talebiniz olursa randomizetrust43@gmail.com adresine yazabilirsiniz. Talepler en geç 30 gün içinde yanıtlanır.

## 9. Çocuklar

Uygulama 13 yaş altındaki kullanıcılara yönelik değildir ve bilerek çocuklardan veri toplamaz.

## 10. Yurt dışına aktarım

Bulut yedeği ve teknik kayıtlar Google altyapısında işlenir ve Google'ın sunucuları yurt dışında bulunabilir. Bulut yedeğini açmayı seçmezseniz hiçbir veriniz cihazınızdan çıkmaz.

## 11. Güvenlik ve sınırları

Güçlü şifreleme kullanıyoruz, ancak hiçbir yöntem tek başına yeterli değildir. Cihazınızda ekran kilidi kullanmanızı öneririz. Cihazınız köklendirilmiş veya kötü amaçlı yazılım bulaşmışsa uygulama içindeki verilerin güvenliği garanti edilemez. Şifre çözme anahtarınızın tüm kopyaları kaybolursa yedek dosyası bir daha açılamaz; bu, yedeğin bizim tarafımızdan okunamamasının doğal sonucudur.

## 12. Değişiklikler

Bu politika güncellenebilir. Güncel metin her zaman bu sayfada yayınlanır ve sayfanın üst kısmındaki tarih değiştirilir. Önemli değişikliklerde uygulama içinde bilgilendirme yapılır.

## 13. İletişim

randomizetrust43@gmail.com

---

# Privacy Policy (English)

Last updated: 10 September 2026

## 1. Summary

Vancrone is an Android app that helps you keep track of your warranties and receipts.

- Everything you enter, including photos and videos, is stored encrypted on your own device.
- We operate no servers. Your records are never sent to us and the developer cannot see them.
- Cloud backup works only if you connect your own Google account. The backup is uploaded to your own Google Drive as a single encrypted file.
- You can turn the backup off and delete it at any time.

## 2. Data controller and contact

The app is published by an independent developer under the name Vancrone. Contact: randomizetrust43@gmail.com

## 3. Data we process

- Records you enter: product name, category, brand or seller, price and currency, purchase date, warranty expiry date, reminder dates, notes and service history.
- Media you add: receipt photos, warranty documents, product images and proof videos.
- Optional location: if you choose to attach a purchase location, an approximate coordinate is saved into that record. Location is never tracked in the background.
- Google account information: if you enable cloud backup, your account name and email address are provided to the app during sign-in. The app requests access only to its own private application data folder in Drive. It cannot see, list or read your other Drive files.
- Technical data: crash reports and anonymous usage events (Firebase Crashlytics and Analytics), advertising identifier (Google AdMob, in the ad supported version) and purchase validation (Google Play Billing). This technical data never contains your record contents, photos, videos, prices or notes.

## 4. Where your data is stored

- On your device: records are stored in a database encrypted with SQLCipher. The encryption key is generated inside the hardware backed Android Keystore and never leaves it. Photos and videos are kept in app private storage that other apps cannot read.
- In your own Google Drive: if you enable cloud backup, your records and media are packed into a single archive, encrypted on the device with AES-256-GCM and only then uploaded. The file is placed in the Drive application data folder, which does not appear in your Drive file list and cannot be read by other apps. The decryption key is stored on your device and additionally backed up through Google Play Services Block Store and, in wrapped form, in the same private Drive folder, so that reinstalling the app with the same account restores your records together with their photos and videos. Downloaded backups are verified with an authentication tag; a modified file is rejected.
- With us: nowhere. We run no servers, databases or archives.

## 5. Permissions

Camera (photos and proof videos), microphone (audio while recording video), notifications (warranty expiry reminders), location (only when you attach a purchase location), photo selection (adding images from the gallery) and internet (cloud backup, ads, crash reporting). All permissions are optional; declining one only disables that feature.

## 6. Third party services

Google Drive, Google Play Services and Block Store, Firebase Crashlytics and Analytics, Google AdMob, Google Play Billing, Google ML Kit and CameraX. Text recognition, barcode and document scanning run on the device. Payment details are handled by Google and never reach the app. These services are provided by Google and are subject to Google's own privacy terms.

## 7. Retention and deletion

Deleted records first go to the in-app trash and can then be removed permanently. You can disable cloud backup and delete the backup file from the app settings. Uninstalling the app removes all local records and media. You can also remove the app's Drive data from drive.google.com under the setting that manages connected apps. Because we never hold your data, no copies remain with us.

## 8. Your rights

Under GDPR and Turkish data protection law (KVKK) you have the right to access, correct, delete, restrict and object to the processing of your data. Since your records live only on your device and in your own Drive, you can exercise all of these rights directly inside the app. You may still write to randomizetrust43@gmail.com and we will respond within 30 days.

## 9. Children

The app is not directed to children under 13 and does not knowingly collect data from them.

## 10. International transfers

Cloud backups and technical reports are processed on Google infrastructure, which may be located outside your country. If you do not enable cloud backup, no data leaves your device.

## 11. Security and its limits

We use strong encryption, but no method is sufficient on its own. We recommend keeping a screen lock on your device. On a rooted or malware infected device the security of in-app data cannot be guaranteed. If every copy of your decryption key is lost, the backup file can no longer be opened; this is the direct consequence of the backup being unreadable by us.

## 12. Changes

This policy may be updated. The current text is always published on this page and the date at the top is changed accordingly. Significant changes are also announced inside the app.

## 13. Contact

randomizetrust43@gmail.com
