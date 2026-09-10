# Vancrone

> Bu dosyanin icerigi, Google Cloud Console > OAuth Branding ekranindaki
> **Application home page** alanina yazacagin adresin **sayfa icerigidir**.
> Yani bu metni web sayfasi olarak yayinla, sonra o sayfanin adresini o alana gir.
> Dosyanin en altindaki "Nasil kullanilir" bolumu sayfaya konmaz, sadece senin icindir.

**Vancrone, satin aldigin urunlerin garanti ve fatura kayitlarini telefonunda sifreli olarak saklayan bir kisisel envanter uygulamasidir.**

Garanti bitis tarihlerini takip eder, sure dolmadan once hatirlatir ve tum urunlerini tek bir listede toplar. Uygulama internetsiz calisir; kayitlarin bir sunucuya gonderilmez.

---

## Vancrone ne yapar?

- **Garanti ve fatura kaydi:** Urun adi, fiyati, para birimi, satin alma ve garanti bitis tarihi, kategori ve gorseller tek kartta toplanir.
- **Kamera ile fatura okuma:** Faturanin fotografini cektiginde uzerindeki yazi cihaz uzerinde okunur ve alanlar otomatik doldurulur. Fotograf bu islem icin hicbir yere gonderilmez.
- **Hatirlatmalar:** Garanti veya iade suresi dolmadan once telefonunda bildirim olusur.
- **Analiz ekrani:** Toplam varlik degeri, kategori dagilimi, aylik harcama ve yaklasan bitis tarihleri, cihazindaki kayitlar uzerinden hesaplanir.
- **Kanit videosu:** Urunun calisir durumunu videoya kaydedip kayitla birlikte saklayabilirsin.
- **Rapor:** Envanterini Excel (CSV) olarak disari aktarabilir, tek urun icin PDF sahiplik belgesi olusturabilirsin.
- **QR etiket ve cihazlar arasi aktarim:** Urun icin QR etiket olusturulur; iki telefon arasinda internetsiz kayit aktarimi yapilabilir.
- **Google Drive yedegi (istege bagli):** Kayitlarin sifrelenip kendi Drive hesabinin uygulamaya ozel klasorune yuklenir.

---

## Verilerin nerede duruyor?

Vancrone "once cihaz" (offline-first) mimarisiyle calisir.

- Tum kayitlar telefonundaki **sifreli veritabaninda** tutulur (SQLCipher ile AES-256).
- Vancrone'nin kayitlarini tutan **bir merkezi sunucusu yoktur**. Gelistirici urun listeni, faturalarini, fotograflarini veya videolarini goremez.
- Yedeklemeyi acarsan dosya **senin kendi Google Drive hesabinin gizli uygulama klasorune** yuklenir. Bu klasor normal Drive listende gorunmez ve baska uygulamalar okuyamaz.
- Yedegi acan sifreleme anahtari senin Google hesabinda saklanir; uygulamayi silip yeniden kurdugunda kayitlarin geri gelebilsin diye.
- Uygulamayi silmek veya "Tum verileri temizle" demek, cihazdaki verileri kalici olarak siler.

---

## Google hesabi izni neden isteniyor?

Vancrone yalnizca **Google Drive uygulama verisi** iznini (`drive.appdata`) ister.

Bu izin, uygulamanin **yalnizca kendi olusturdugu gizli klasore** erisim verir. Vancrone senin Drive'indaki diger dosyalari, fotograflarini veya belgelerini goremez, listeleyemez ve degistiremez. Izin sadece sifreli yedek dosyasini yazmak ve geri yuklemek icin kullanilir.

Izni istedigin zaman Google Hesabim > Guvenlik > Ucuncu taraf uygulamalar bolumunden geri alabilirsin.

---

## Ucretlendirme

Vancrone su anda ucretsizdir. Ucretsiz surumde reklam gosterilir. Ileride sunulacak Pro ve Business yukseltmeleri tek seferlik odemedir ve odeme islemi tamamen Google Play Faturalandirma uzerinden yurur; kart bilgilerin gelistiriciye ulasmaz.

---

## Uygulamada kullanilan ucuncu taraf hizmetler

- **Google Play Faturalandirma** - satin alma islemleri
- **Google AdMob** - ucretsiz surumdeki reklamlar
- **Firebase Crashlytics** - cokme raporlari
- **Google Drive (appDataFolder)** - istege bagli sifreli yedek
- **Cihaz ici metin tanima** - fatura okuma (fotograf disari cikmaz)

---

## Yasal belgeler

- Kullanici Sozlesmesi: `KULLANICI_SOZLESMESI_ADRESI`
- Gizlilik Politikasi: `GIZLILIK_ADRESI`
- KVKK / GDPR Aydinlatma Metni: `AYDINLATMA_ADRESI`

---

## Iletisim

Gelistirici: `TAM_AD_BURAYA`
E-posta: randomizetrust43@gmail.com

Son guncelleme: 10 Eylul 2026

---

## Nasil kullanilir (bu bolum sayfaya konmaz)

1. Yukaridaki `KULLANICI_SOZLESMESI_ADRESI`, `GIZLILIK_ADRESI`, `AYDINLATMA_ADRESI` ve `TAM_AD_BURAYA` yer tutucularini gercek degerlerle degistir.
2. Bu dosyayi yayinla. Paketteki `docs/index.html` zaten bu metinden uretildi; oldugu gibi kullanabilirsin.
3. Google Cloud Console > OAuth Branding ekraninda:
   - **Application home page** = bu sayfanin adresi (ornek: `https://kullaniciadi.github.io/vancrone-legal/`)
   - **Application privacy policy link** = gizlilik sayfasinin adresi
   - **Application terms of service link** = kullanici sozlesmesi sayfasinin adresi
   - **Authorized domains** = adresin alan adi, basinda `https://` olmadan (ornek: `github.io` degil, dogrulanabilen kendi alan adin; GitHub Pages kullaniyorsan `kullaniciadi.github.io`)
4. Uc adres de **ayni alan adinda** olmali ve ana sayfa gizlilik politikasina link vermeli. Paketteki sayfalar bu kurala gore hazirlandi.
