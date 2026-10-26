# Privacy Policy & Data Security

> This document is the comprehensive English policy governing the data processing principles, security measures, and privacy standards of the Vancrone application. Last updated: October 15, 2026.

## 1. Introduction

This Privacy Policy explains how information is handled in connection with the Vancrone Android application. We founded this policy on a single fundamental truth: We, the Developer, do not see, collect, or store your personal inventory, receipts, invoices, or photos. This policy explains what that means in practice and describes the limited technical data collected through the Google services integrated into the app, as well as the information you choose to send through the feedback form.

Data Controller: Vancrone is developed and published by an independent sole developer, referred to herein as the "Developer". You can contact the Developer at vancrone.app@gmail.com; verified publisher details are displayed on Vancrone's Google Play store page. Because your warranty records, invoices, and photos remain exclusively in your device's local offline storage, the Developer never receives this content and does NOT act as a data controller for it. The Developer is the data controller strictly and exclusively for the limited data described in Sections 6, 7 and 14: crash reports, messages you send through the feedback form, and, if in-app purchases are introduced, purchase records provided by Google Play.

## 2. Our Philosophy: Offline-First by Design

Vancrone is built upon an "offline-first" architecture. There is no centralized Vancrone server that stores, indexes, or accesses the product data, prices, dates, notes, invoice photos, or proof videos that you enter into the Application. This is not merely a policy promise; it is a conscious architectural choice ("privacy by design").

## 3. Data We Do Not Collect

We do NOT collect, transmit, view, sell, rent, or access:

- Your product inventory and warranty records (names, prices, dates, return periods, service records, notes);
- Your invoice and receipt scans or vault proof videos;
- Financial summaries and risk analyses generated locally by the Application.

This data is created exclusively by you and resides on your device until you independently decide to export or share it.

## 4. Data Stored Locally on Your Device

Your records (product names, prices, dates, return periods, service records, and notes on where physical documents are kept) are stored in a local on-device database encrypted with AES-256 via SQLCipher. The database key is generated on your device and stored in EncryptedSharedPreferences, protected by a key held in the Android Keystore (hardware-backed on devices that support it). Invoice photos, product images, and proof videos are stored in the app's private storage area, which Android isolates from other apps and protects with the device's own storage encryption; Vancrone does not apply an additional encryption layer to these media files. On a rooted device, other apps may be able to bypass these protections.

## 5. Encrypted Manual Backup via Storage Access Framework (SAF)

Vancrone does NOT connect to Google Drive API and operates NO cloud backup servers. Instead, Vancrone provides a local backup utility leveraging Android's Storage Access Framework (SAF):

- Manual Encrypted Export: When you start a backup in Settings, your database, warranty media (invoice photos, product images, proof videos), and images saved with the Thermal Receipt Restorer are archived and encrypted into a single backup file (.vcb) using AES-256-GCM.
- Optional Backup Password: If you set a backup password, the encryption key is derived from that password (PBKDF2-HMAC-SHA256, 600,000 iterations) and the file cannot be opened without it. The Developer cannot recover a forgotten password. If you do not set a password, the file is encrypted with a key built into the app: you can still restore it on any device, but anyone who obtains both the file and the Vancrone app can open it. We recommend setting a password, especially if you keep the backup in a shared location or cloud storage.
- Complete User Control: This file is written strictly to the location chosen by you via Android’s SAF file picker (such as internal memory, SD card, USB drive, or PC).
- Zero Server Access: This backup file is never transmitted to the Developer or any external cloud servers by Vancrone. The preservation, off-device transfer, and security of this backup archive rests entirely and exclusively with the user.

## 6. Third-Party Services Utilized by Vancrone

To function properly, Vancrone integrates a minimal set of standard Google SDKs. Where these SDKs send data, Google processes it on behalf of the Developer under Google's data processing terms.

- Google Firebase Crashlytics — Crash Diagnostics: When the app crashes or a handled error occurs (for example, a failed PDF or CSV export), Crashlytics sends a report containing the stack trace, device model, Android version, app version, a random Crashlytics installation identifier, and the time of the event. Reports do not contain your records, invoices, or photos and are not linked to your name or email address. They are used only to diagnose bugs and are retained by Crashlytics for 90 days.
- Google AdMob — Advertisements (planned): The current version of Vancrone does not display ads and does not include the Google Mobile Ads (AdMob) SDK. If ads are introduced for the free tier in a future version, this policy will be updated before that release, and personalized ads will only be shown with your consent where the law requires it.
- Google ML Kit — On-Device Text Recognition (OCR) and Document Scanner: Vancrone’s receipt scanner uses ML Kit's on-device text recognition and the document scanner provided by Google Play services. Scanned photos and extracted text are processed entirely on your phone and are never transmitted to Google servers. ML Kit may contact Google to download model updates and to send limited metrics about the performance of the API itself, which do not include your images or text.
- Google Play Billing — Digital Purchases: The current version of Vancrone offers no in-app purchases and does not connect to Google Play Billing. If optional Pro or Business upgrades are introduced, they will be processed entirely by Google Play: payment details will be handled solely by Google, the Developer will only receive the order information Google Play provides (such as order number, product, purchase date, and country), and the app will read your purchase status on the device through the Google Play Billing Library. This policy will be updated before that happens.

## 7. No Server-Side Infrastructure; Feedback Form

Vancrone operates no servers of its own. The Developer maintains no cloud backend, no user accounts, and no remote database for your records. Apart from the Google services described in Section 6, data leaves your device only when you initiate it:

- Feedback: When you tap Send in Settings > "Report a Bug & Feedback", the app itself transmits nothing; it opens your own email app with a prepared email to vancrone.app@gmail.com containing your message, your device manufacturer and model, Android version, and app version. You can review and edit it before sending; it reaches the Developer's Gmail (Google) mailbox, together with your email address, only if you send it from your own email account. This information is used only to reply to you and to fix the reported problem, and is kept only as long as needed for that purpose. Please do not include sensitive personal data in feedback messages.
- Export and Sharing: PDF/CSV reports, backups, and files you share go only to the destination you choose.

## 8. Security Measures

Beyond AES-256 local database encryption, Vancrone uses parameterized database queries to prevent SQL injection, decodes and downscales images on the device before passing them to the local OCR engine, verifies backup integrity (authenticated AES-GCM encryption and SHA-256 checksums of the archived files) before restoring, and warns you if signs of root access are detected. The current version offers no purchases; if purchases are introduced, their status will be read from Google Play through the Google Play Billing Library, and Vancrone does not perform its own server-side verification of purchase signatures. However, no software security system is impenetrable, and you remain responsible for maintaining your physical device's security.

## 9. Data Retention and User Control

Because your data is stored locally, complete direct control belongs to you:

- In-App "Clear All Data": Permanently and irreversibly deletes all warranty records in your local encrypted database together with their attached invoice photos, product images, and proof videos. It also deletes images saved with the Thermal Receipt Restorer, as well as media files and temporary camera captures left in the app's private storage without a linked record.
- Uninstalling the Application: Triggers Android’s operating system to permanently wipe all private application storage directories.
- The Developer maintains no off-device copies of your records and cannot recover deleted records. Backup files you exported remain wherever you saved them until you delete them.
- Crash reports and feedback messages are retained only for the periods described in Sections 6 and 7.

## 10. Children's Privacy

Vancrone is not directed to children under the age of 13, and the Developer does not knowingly collect personal data from children.

## 11. User Choices and Privacy Controls

- Ads and Advertising ID: The current version shows no ads and does not collect your Advertising ID.
- Crash Reports: You can turn off Crashlytics at any time in Settings > About > "Crash Reports". The switch is on by default. While it is off, no crash reports are sent and reports still waiting on your device are deleted; your choice is kept until you change it. Reports sent before you turned the switch off are retained for the period described in Section 6. Uninstalling the app also stops all collection.
- Backup: You may export or restore an encrypted manual backup (.vcb) at any time via Settings using the Storage Access Framework (SAF), and protect it with a backup password.
- Data Deletion: You can wipe all data at any time via Settings > "Clear All Data".

## 12. International Data Transfers

Because our service provider (Google) operates globally, the crash reports and feedback messages described in Sections 6 and 7, as well as Google Play order data if purchases are introduced, may be processed outside your home country, including within the United States. For such transfers Google relies on its data processing terms, including Standard Contractual Clauses (SCCs) and, where applicable, the EU-U.S. Data Privacy Framework.

## 13. Your Privacy Rights

Under applicable data protection laws (GDPR, CCPA, KVKK, APPI), you possess rights regarding your data, such as access, correction, deletion, and objection. Because your inventory and receipts never reach the Developer, you can exercise these rights for that content directly on your device. For crash reports or feedback messages, contact vancrone.app@gmail.com; because crash reports are pseudonymous, the Developer may not be able to identify which entries relate to you.

## 14. Region-Specific Disclosures

- EEA, UK, and Switzerland: The legal bases for processing limited technical data are legitimate interests (crash diagnostics to keep the app stable; answering feedback you send) and, if in-app purchases are introduced, contract performance (in-app billing). If personalized ads are introduced, they will be based on your consent. You have the right to object to processing based on legitimate interests and to lodge a complaint with your local supervisory authority.
- United States: The Developer does not sell or share personal information within the meaning of the California Consumer Privacy Act (CCPA).
- Japan: Personal data is handled in accordance with the Act on the Protection of Personal Information (APPI).
- Turkey: Inquiries regarding KVKK Article 11 can be directed to vancrone.app@gmail.com.

Please note that Vancrone is maintained by an independent sole developer; emails are reviewed in good faith within reasonable timeframes based on active development availability.
