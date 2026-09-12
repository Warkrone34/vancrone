# Privacy Policy & Data Security

> This document is the comprehensive English policy governing the data processing principles, security measures, and privacy standards of the Vancrone application. Last updated: September 11, 2026.

## 1. Introduction

This Privacy Policy explains how information is handled in connection with the Vancrone Android application. We founded this policy on a single fundamental truth: We, the Developer, do not see, collect, or store your personal inventory, receipts, invoices, or photos. This policy explains what that means in practice and outlines the limited technical data collected by our integrated third-party service providers.

Data Controller: Vancrone is developed and published by an independent sole developer, referred to herein as the "Developer". You can contact the Developer at vancrone.app@gmail.com; verified publisher details are displayed on Vancrone's Google Play store page. Because your warranty records, invoices, and photos remain exclusively in your device's local offline storage, the Developer never receives this content and does NOT act as a data controller for it. The Developer is the data controller strictly and exclusively for the limited technical diagnostics, anonymous crash reports, advertising, and purchase verification data described in Sections 6 and 14.

## 2. Our Philosophy: Offline-First by Design

Vancrone is built upon an "offline-first" architecture. There is no centralized Vancrone server that stores, indexes, or accesses the product data, serial numbers, prices, dates, notes, invoice photos, or proof videos that you enter into the Application. This is not merely a policy promise; it is a conscious architectural choice ("privacy by design").

## 3. Data We Do Not Collect

We do NOT collect, transmit, view, sell, rent, or access:

- Your product inventory and warranty records (names, prices, dates, serial numbers, notes);
- Your invoice and receipt scans or vault proof videos;
- Financial summaries and risk analyses generated locally by the Application.

This data is created exclusively by you and resides on your device until you independently decide to export or share it.

## 4. Data Stored Locally on Your Device

All User Content is stored in a local on-device database and protected by AES-256 encryption; this is implemented via SQLCipher for the structured database and Android's hardware-backed EncryptedSharedPreferences for configuration and preference keys. AES-256 is the gold standard of encryption utilized by financial institutions and government agencies worldwide.

## 5. Encrypted Manual Backup via Storage Access Framework (SAF)

Vancrone does NOT connect to Google Drive API and operates NO cloud backup servers. Instead, Vancrone provides a secure, modern local backup utility leveraging Android's Storage Access Framework (SAF):

- Manual Encrypted Export: When you initiate "Backup (Export)" in Settings, your database, vault proofs, and invoice images are archived and encrypted into a single backup file (.vcb) using AES-256-GCM.
- Complete User Control: This file is written strictly to the location chosen by you via Android’s SAF file picker (such as internal memory, SD card, USB drive, or PC).
- Zero Server Access: This encrypted backup file is never transmitted to the Developer or any external cloud servers. The preservation, off-device transfer, and security of this backup archive rests entirely and exclusively with the user.

## 6. Third-Party Services Utilized by Vancrone

To function properly, Vancrone integrates a minimal set of standard Google SDKs:

- Google Firebase Crashlytics — Crash Diagnostics: We use Firebase Crashlytics to receive anonymous stack traces when errors occur, allowing us to diagnose bugs and improve app stability.
- Google AdMob — Advertisements (Free Tier): For users of the free tier, Google AdMob is utilized to serve and measure banners and rewarded ads.
- Google ML Kit — On-Device Text Recognition (OCR): Vancrone’s receipt scanner utilizes Google ML Kit's on-device text recognition. Scanned photos and extracted text are processed entirely on your phone and are never transmitted to Google servers.
- Google Play Billing — Digital Purchases: Upgrades to Pro and Business "Lifetime" tiers are processed entirely by Google Play Billing; financial payment data is handled solely by Google.

## 7. No Server-Side Infrastructure

Vancrone operates no servers. The Developer maintains no cloud backend, no user accounts, and no remote database. Other than the Google SDK diagnostics described in Section 6, no data leaves your device to any service operated by the Developer.

## 8. Security Measures

Beyond AES-256 local database encryption, Vancrone enforces strict input sanitization to prevent injection vulnerabilities, verifies file integrity before invoking the local OCR engine, and verifies digital cryptographic purchase signatures returned by Google Play. However, no software security system is impenetrable, and you remain responsible for maintaining your physical device's security.

## 9. Data Retention and User Control

Because your data is stored locally, complete direct control belongs to you:

- In-App "Clear All Data": Instantly, permanently, and irreversibly destroys your local encrypted database, vault records, and media files.
- Uninstalling the Application: Triggers Android’s operating system to permanently wipe all private application storage directories.
- The Developer maintains no off-device copies and cannot recover deleted records.

## 10. Children's Privacy

Vancrone is not directed to children under the age of 13, and the Developer does not knowingly collect personal data from children.

## 11. User Choices and Privacy Controls

- Ads: You may opt out of personalized ads or reset your Advertising ID via Android Settings > Google > Ads, or eliminate ads entirely by upgrading to Pro/Business.
- Backup: You may export or restore an encrypted manual backup (.vcb) at any time via Settings using the Storage Access Framework (SAF).
- Diagnostics: You can disable diagnostic data sharing through your Android system privacy settings.
- Data Deletion: You can wipe all data at any time via Settings > "Clear All Data".

## 12. International Data Transfers

Because our service provider (Google) operates globally, the limited technical diagnostic and advertising data described in Section 6 may be processed outside your home country, including within the United States, pursuant to Standard Contractual Clauses (SCCs).

## 13. Your Privacy Rights

Under applicable data protection laws (GDPR, CCPA, KVKK), you possess rights regarding your data. Because your inventory and receipts never reach the Developer, you can exercise access, correction, and deletion directly on your device.

## 14. Region-Specific Disclosures

- EEA, UK, and Switzerland: The legal bases for processing limited technical data are legitimate interests (diagnostics), consent (personalized ads), and contract performance (in-app billing). You have the right to lodge a complaint with your local supervisory authority.
- United States: The Developer does not sell or share personal information within the meaning of the California Consumer Privacy Act (CCPA).
- Japan: Personal data is handled in accordance with the Act on the Protection of Personal Information (APPI).
- Turkey: Inquiries regarding KVKK Article 11 can be directed to vancrone.app@gmail.com.

Please note that Vancrone is maintained by an independent sole developer; emails are reviewed in good faith within reasonable timeframes based on active development availability.