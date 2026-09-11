# Vancrone

**Vancrone is a personal inventory app that keeps the warranty and invoice records of the products you buy encrypted on your phone.**

It tracks warranty expiry dates, reminds you before they run out, and gathers all your products in a single list. The app works without an internet connection; your records are not sent to a server.

---

## What does Vancrone do?

- **Warranty and invoice records:** Product name, price, currency, purchase date and warranty expiry date, category, and images are gathered on a single card.
- **Invoice reading with the camera:** When you take a photo of an invoice, the text on it is read on the device and the fields are filled in automatically. The photo is not sent anywhere for this process.
- **Reminders:** A notification is created on your phone before the warranty or return period runs out.
- **Analysis screen:** Total asset value, category breakdown, monthly spending, and upcoming expiry dates are calculated from the records on your device.
- **Proof video:** You can record a video showing that the product works and keep it together with the record.
- **Reports:** You can export your inventory as Excel (CSV) and create a PDF ownership document for a single product.
- **QR labels and device-to-device transfer:** A QR label is created for a product; records can be transferred between two phones without an internet connection.
- **Google Drive backup (optional):** Your records are encrypted and uploaded to the app-specific folder of your own Drive account.

---

## Where is your data kept?

Vancrone works with a "device first" (offline-first) architecture.

- All records are kept in an **encrypted database** on your phone (AES-256 with SQLCipher).
- Vancrone has **no central server** that holds your records. The developer cannot see your product list, your invoices, your photos, or your videos.
- If you turn backup on, the file is uploaded to the **hidden app folder of your own Google Drive account**. This folder does not appear in your normal Drive list and other apps cannot read it.
- The encryption key that opens the backup is stored in your Google Account, so that your records can come back when you delete the app and install it again.
- Deleting the app or choosing "Clear all data" permanently deletes the data on the device.

---

## Why is Google Account permission requested?

Vancrone requests only the **Google Drive application data** permission (`drive.appdata`).

This permission gives access **only to the hidden folder the app creates itself**. Vancrone cannot see, list, or change the other files, photos, or documents in your Drive. The permission is used only to write and restore the encrypted backup file.

You can withdraw the permission whenever you want from Google Account > Security > Third-party apps.

---

## Pricing

Vancrone is currently free. Ads are shown in the free version. The Pro and Business upgrades to be offered in the future are one-time payments, and the payment is handled entirely through Google Play Billing; your card details do not reach the developer.

---

## Third-party services used in the app

- **Google Play Billing** - purchase transactions
- **Google AdMob** - ads in the free version
- **Firebase Crashlytics** - crash reports
- **Google Drive (appDataFolder)** - optional encrypted backup
- **On-device text recognition** - invoice reading (the photo does not leave the device)

---

## Legal documents

- User Agreement: `https://github.com/Warkrone34/vancrone/blob/main/User%20Agreement%20%26%20Anti-Theft%20(EULA).md`
- Privacy Policy: `https://github.com/Warkrone34/vancrone/blob/main/Privacy%20Policy%20%26%20Data%20Security.md`
- KVKK / GDPR Disclosure Text: `https://github.com/Warkrone34/vancrone/blob/main/KVKK%20Notice%20%26%20Disclaimer.md`

---

## Contact

E-mail: vancrone.app@gmail.com

Last updated: 11 September 2026

---
