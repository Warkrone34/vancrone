# 2. Privacy Policy & Data Security

> Bu belge Vancrone uygulamasinin icinde gosterilen metnin birebir aynisidir. Son guncelleme: 11 Eylul 2026.

## 1. Introduction

This Privacy Policy explains how Developer handles information in connection with the Vancrone Android application. We built this policy around one central fact: we, the Developer, do not see your personal inventory, invoices, or photos. This policy explains exactly what that means, and what limited data our third-party service providers do collect.

Who is responsible: Vancrone is developed and published by an independent developer, referred to in this policy as the Developer. You can reach the Developer at vancrone.app@gmail.com, and the publisher details verified by Google are shown on the Vancrone listing on Google Play. Because your warranty records, invoices, and photos stay on your own device and, if you turn on backup, inside your own Google Drive, the Developer never receives that content and does not act as its data controller. The Developer acts as a data controller only for the limited diagnostic, advertising, and purchase-validation data described in Section 6 and Section 14.

## 2. Our Approach: Local-First by Design

Vancrone is built on an "offline-first" architecture. There is no central Vancrone server that stores, indexes, or has access to the product information, prices, dates, notes, invoice photos, or proof videos you enter into the App. This is a deliberate architectural choice — sometimes called "privacy by design" — not just a policy promise.

## 3. Data We Do Not Collect

We do not collect, transmit, view, sell, rent, or otherwise access:

- Your product inventory records (names, prices, dates, warranty terms, notes);
- Your invoice or receipt photos or proof videos;
- The financial risk summaries the App generates for you.

This data is created by you and stays on your device — and, if you choose, in your own personal Google Drive — unless and until you decide to share or export it yourself.

## 4. Data Stored Locally on Your Device

All User Content is stored in a local database on your device, protected using AES-256 encryption, implemented through SQLCipher (for the database) and Android's EncryptedSharedPreferences (for smaller configuration and preference data). AES-256 is the same encryption standard widely used by financial institutions and government systems to protect sensitive information.

## 5. Optional Cloud Backup via Your Google Drive

Vancrone offers an optional backup feature that, if you turn it on, encrypts and syncs your data to your own personal Google Drive account using Google's restricted appDataFolder scope. In practice, that means:

- Your backup lives in a special, hidden application-data folder tied specifically to Vancrone — it does not appear in your regular Google Drive file list, and other apps cannot see it.
- Syncing happens directly between your device and your Google Account; the Developer does not operate a server in between and has no access to this backup data.
- Your backup is governed by your Google Account and by Google's own Privacy Policy and Terms of Service.
- If you disable this feature, delete the backup from your Google Account, or revoke Vancrone's Drive access in your Google Account permissions, the backup is removed accordingly.

## 6. Third-Party Services Used by Vancrone

Even though Vancrone has no central server for your inventory data, it relies on a small number of Google services to function, and each generates its own limited data:

- Google Firebase Crashlytics — Crash Reporting: We use Firebase Crashlytics to understand when and why the App crashes, so we can fix bugs.
- Google AdMob — Advertising (Free Tier): If you use the free version of Vancrone, we use Google AdMob to show banner and rewarded ads.
- Google ML Kit — On-Device Invoice Scanning (OCR): Vancrone's invoice scanner uses Google ML Kit's on-device text recognition. Your invoice photos, and the text extracted from them, are processed entirely on your device and are not uploaded to Google or anyone else for this feature.
- Google Play Billing — Purchases: Purchases of the Pro and Business "Lifetime" upgrades are processed entirely by Google Play Billing.

## 7. No Server-Side Infrastructure

Vancrone does not operate any server. The Developer runs no backend service for your inventory data, for your license, or for anything else. Pro and Business purchases are verified on your own device through Google Play Billing, and no purchase information is sent to a server operated by the Developer. Apart from the optional backup stored in your own Google Drive account and the crash diagnostics described in Section 6, no data leaves your device to any service run by the Developer.

## 8. Security Measures

Beyond the local AES-256 encryption described above, we apply technical safeguards appropriate to Vancrone's architecture, including: input sanitization to guard against injection-style attacks; validation of uploaded or scanned files before they reach the on-device OCR engine; and cryptographic signature verification of the purchase data returned by Google Play Billing on your device, to prevent spoofed purchase events. No security measure is perfect, and we cannot guarantee absolute security.

## 9. Data Retention and Your Control

Because your data lives on your device, you're in control of it:

- In-App "Clear All Data": Permanently and irreversibly deletes your local encrypted database and associated media.
- Uninstalling the App: Also permanently and irreversibly deletes this data from your device.
- We do not retain a copy of this data anywhere, because we never had one.

## 10. Children's Privacy

Vancrone is not directed at children, and we do not knowingly collect personal data from children without appropriate consent.

## 11. Your Choices

- Ads: Limit ad personalization or reset your Advertising ID in your Android device settings, or remove ads entirely by upgrading to Pro/Business.
- Cloud backup: Turn Google Drive backup on or off at any time in the App's settings.
- Diagnostics: Where your device or Android version provides an OS-level opt-out for diagnostic data sharing, that setting is respected.
- Your data: Use "Clear All Data" or uninstall the App at any time, as described in Section 9.

## 12. International Data Transfers

Because our service providers (Google) operate globally, some of the limited data described in Section 6 — such as Crashlytics diagnostics, AdMob advertising data, or Play Billing purchase data — may be processed outside your own country, including in the United States.

## 13. Your Privacy Rights

Depending on where you live, you may have rights to access, correct, delete, or restrict the limited data described in this policy, and to object to certain processing (such as ad personalization). Because most of your data never reaches us in the first place, you can already exercise many of these rights directly through the App (Section 9) or through your Google Account settings.

## 14. Region-Specific Privacy Information

- European Economic Area, United Kingdom, and Switzerland: The Developer is the controller for the limited data described in this policy. The legal bases are legitimate interest for crash and stability diagnostics, your consent for personalized advertising, and performance of a contract for validating purchases you make through Google Play. You have the right to request access, correction, deletion, restriction, and portability, to object to processing, and to withdraw consent at any time. Personalized advertising is shown only where you have given consent through the consent request presented in the App, and you can change that choice at any time. The Developer does not sell personal data. Diagnostic and advertising data may be processed by Google outside your country under the safeguards Google applies as a service provider. You may lodge a complaint with your national supervisory authority, for example the Information Commissioner's Office in the United Kingdom or the Federal Data Protection and Information Commissioner in Switzerland.
- Japan: The handling business operator is the Developer, reachable at vancrone.app@gmail.com. The purposes of use are limited to diagnosing crashes, keeping the App stable, showing advertising, and validating purchases. Personal information may be provided to Google as a service provider and may be processed outside Japan, including in the United States. You may request disclosure, correction, or suspension of use of your personal information by writing to the address above.
- United States: Vancrone is not directed to children under 13, and the Developer does not knowingly collect personal information from children under 13. The Developer does not sell or share personal information as those terms are used under California law. You can limit ad personalization at any time in your device settings, under Google and then Ads.
- Türkiye: Your rights under Article 11 of Law No. 6698 (KVKK) are set out in the GDPR/KVKK Disclosure Text. You may contact the Developer first, and you may also complain to the Personal Data Protection Authority.
- Other countries: Where the law of the country where you live gives you rights beyond this policy, including Brazil, Mexico, Canada, Australia, Taiwan, Hong Kong, and Singapore, those rights apply. You may contact the Developer at vancrone.app@gmail.com or your local authority.
