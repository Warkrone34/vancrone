# Vancrone Homepage Guide & Feature Overview

> This document is the official user manual describing the home screen, warranty tracking, tools, and security features of Vancrone. Last updated: October 16, 2026.

---

## 1. Overview & Offline-First Architecture

Vancrone is an independent digital inventory and vault that tracks warranty periods, return periods, invoices, and proof of ownership for the items you buy. The current version is free: every feature is available without limits, and there are no ads or in-app purchases.

- **Offline & Local Storage:** Your records, invoices, and photos never leave your device; there is no Vancrone server, user account, or cloud database. Only crash reports without any of your content are sent to Google Firebase Crashlytics, and you can turn this off in **Settings > About > Crash Reports** (see the Privacy Policy).
- **Encrypted Local Vault:** Your records are stored in an AES-256 encrypted database (SQLCipher). Invoice photos, documents, and videos are kept in the app's private storage on your device.
- **User Responsibility & Backups:** Because your data exists only on your device, you are responsible for regular backups. If your device is lost, reset, or damaged, the developer cannot recover your data. Use **Settings > Data Management > Backup (Export)** to save an encrypted `.vcb` file to a place you choose, optionally protected with a password, and **Restore (Import)** to bring it back on the same or a new phone.

---

## 2. Top App Bar

- **Calendar:** The calendar icon opens a monthly calendar of warranty expiry dates. Tap a day to see the items that expire on it.
- **User Guide & F.A.Q.:** The question-mark icon opens in-app answers about backups, privacy, scanning, reports, and more.
- **Selection Mode:** Long-press any warranty card to start selecting. The top bar then shows how many items are selected and lets you move them all to the trash at once or cancel.

---

## 3. Secured Assets Card

The card at the top of the list shows the total value of your registered items.

- **Totals by Currency:** Amounts are added up separately for each currency (for example ₺, $, €, ¥); currencies are not converted into one another.
- **Breakdown:** Tap the card to expand or collapse the per-currency breakdown.

---

## 4. Search, Sort & Filter

- **Search Bar:** Filters the list as you type, by product name or category. Includes a one-tap clear button.
- **Sort Chips:** **Date Added**, **Expiry Date**, and **Name**. Tap the active chip again to reverse the order.
- **Currency Filter:** Shows **All Products** or only the items registered in one currency.

---

## 5. Warranty Cards

Each card shows the product image or icon, the product name, its category (Electronics, Clothing & Fashion, Home & Living, Automotive, Personal Care, Other), the price, and a countdown badge:

- **Theme colour:** 30 days or more left.
- **Orange:** fewer than 30 days left.
- **Red:** fewer than 3 days left. In the last 24 hours, the badge counts down in hours, minutes, and seconds.
- **Dark red:** the warranty has expired.

Tap a card to open the product detail; long-press it to start selection mode. Warranty end dates include any extra warranty period carried over with a QR transfer.

---

## 6. Adding Items (+ Button)

The `+` button in the lower-right corner opens three options:

- **Add Manually:** A form for the product name, icon, price and currency, category, expiry date, and **Return Right** (1–90 days, 14 by default). Under **Docs & Evidence**, the **Add invoice or document** button lets you attach up to 5 photos or PDFs at once (large photos are reduced automatically, PDFs up to 50 MiB), plus a product image and a proof video; you also record where the physical copy is kept. **Serial Entry Mode** keeps the form open after saving so you can enter several items in a row.
- **Warranty Capture (Beta):** Photograph or choose a receipt, invoice, or warranty document. The text is read on your device and the product name, price, currency, and dates are suggested; values that are not clearly stated are marked "Estimated". Always check the fields against the original before saving. The scanned image is added to the item's documents.
- **Thermal Receipt Restorer:** Makes faded thermal receipts easier to read with contrast and sharpening filters, and keeps the results in its own archive.

A scroll-to-top button appears when you scroll down the list.

---

## 7. Product Detail

- **Invoices & Documents:** All attached photos and PDFs; tap one to view it in full size or open the PDF.
- **Possible Return Active:** Shows the days left in the return period you entered. Return conditions vary by country and category.
- **Proof Video:** Play or download the timestamped proof video.
- **Service History:** Add service records with a title, description, and cost.
- **Options menu:** **Edit**, **Share / Sale Ad** (copies a ready-made sale text), **Create PDF Certificate**, **Share Proof Video**, **Transfer (Air Gap)** to another phone via QR code, **Where is the Physical Copy?**, and **Delete** (moves the item to the trash).

---

## 8. Bottom Navigation Bar

- **Warranties (Home):** Your inventory list and the Secured Assets card.
- **Analytics:** Total Asset Value, Approaching Expirations, number of items, Avg. Warranty Life, Most Valuable Item, Category Distribution, and Monthly Warranty Entries for the last 6 months. All calculations run on your device.
- **Tools:**
  - **Receive Transfer (Air Gap):** Scan the QR code shown on the sending phone to add the item. The QR code carries the product name, price, currency, dates, extra warranty period, and category in readable form; photos and documents are not transferred.
  - **Thermal Receipt Restorer**
  - **PDF Certificate:** Creates a PDF inventory report of all your items.
  - **Excel (CSV) Export:** Exports your inventory as a spreadsheet.
  - **Inventory Video** and **Theme & Appearance:** Short guides to the proof video feature and the appearance settings.
- **Settings:**
  - **General:** Theme (system, light, dark), Theme Accent, Animated Background, Language, and Notifications.
  - **Data Management:** Backup (Export), Restore (Import), Trash Bin (restore or permanently delete items), and Clear All Data (asks for confirmation twice).
  - **About:** Report a Bug & Feedback, Crash Reports, Legal Terms & Privacy, and Version.

---

## 9. Notifications & Home Screen Widget

- **Reminders:** With notification permission, Vancrone reminds you 30, 7, 3, and 1 day before a warranty ends and on the last day, 2 days before a return period ends, and periodically to back up your data. It also sends occasional tips and seasonal messages. Delivery depends on your phone's battery and notification settings.
- **Widget:** Add the Vancrone widget to your home screen to see how many items are safe, expiring, or critical without opening the app.

---

## 10. Security Notes

- **Rooted devices:** If signs of root access are detected, Vancrone shows a warning; you can continue at your own risk or exit.
- **Lost encryption key:** If the phone's encryption key becomes unavailable, Vancrone keeps the unreadable records in a separate folder and offers to restore from a backup or start with an empty vault.

---

## 11. Support & Feedback

- Open **Settings > About > Report a Bug & Feedback** to send a bug report or suggestion (up to two per day). Your email app opens with your message and basic device and app version information ready; you send it to the developer from there.
- You can also reach the developer through the verified Google Play Store listing.
- *To protect against spam crawlers and automated bots, email addresses are intentionally not published in plain text in this guide.*
