# Vancrone Homepage Guide & Feature Overview

> This document is the official user manual describing the architecture, warranty tracking mechanics, and security features of the Vancrone home screen. Last updated: September 12, 2026.

---

## 1. Overview & Offline-First Architecture

Vancrone is an independent digital inventory and security vault designed to reliably track warranty periods, receipts, serial numbers, and proof of ownership for your purchased items.

- **Strictly Offline & Local Storage:** Vancrone never sends your personal data to remote servers or cloud databases. All external cloud API dependencies (including Google Drive API bureaucracy) have been completely eliminated.
- **Encrypted Local Vault:** All item records, receipt photographs, and attachments are encrypted and stored solely on your device using Room SQLCipher.
- **User Responsibility & Backups:** Because your data resides entirely on your device, you are solely responsible for creating regular backups. If your device is lost, factory reset, or damaged, data cannot be recovered by the developer. Use **Settings > Data Security & Backup** to export an encrypted `.vcb` backup file to your external storage or USB drive.

---

## 2. Top App Bar & Quick Navigation

Located at the top of the homepage, the Vancrone Top Bar offers streamlined navigation and batch management tools:

- **App Title & Plan Badge:** Tapping returns the list smoothly to the top. Displays your active tier (PRO / BUSINESS) dynamically.
- **Calendar View:** The calendar icon in the top right provides a visual monthly matrix of all upcoming warranty expiration dates.
- **Frequently Asked Questions (FAQ):** The question mark icon directs you immediately to in-app tips, guides, and troubleshooting steps.
- **Batch Selection Mode:** Long-pressing any warranty card activates multi-selection mode, allowing you to select multiple items and move them to the trash bin in a single action.

---

## 3. Multi-Currency Asset & Guarantee Card

Positioned prominently at the top of the list, this dynamic gradient card provides an instant financial valuation of your protected assets:

- **Primary Currency Valuation:** Calculates the total real-time value of all registered warranties based on your selected default currency (e.g., $, €, ₺, ¥).
- **Multi-Currency Breakdown:** Tapping the card expands a breakdown detailing expenditures logged in other currencies (EUR, USD, GBP, JPY, etc.).
- **Security Badge:** Visual confirmation that your asset records are secured locally under device encryption.

---

## 4. Search, Filter & Dynamic Sorting

Find any product in your inventory within seconds using intelligent management tools:

- **Live Search Bar:** Filters instantly as you type product names, stores, or serial numbers. Includes a one-tap clear button.
- **Sorting Chips:**
  - **Date Added:** Sort items chronologically by when they were added (ascending or descending).
  - **Expiry Date:** Highlights expiring items first so you never forfeit warranty claims or return periods.
  - **Name:** Alphabetical order from A to Z or Z to A.
- **Currency Filter Chip:** A dropdown filter to isolate products registered under a specific currency.

---

## 5. Smart Warranty & Inventory Cards

Each product card presents all critical product data at a glance:

- **Visual Identity:** High-resolution product thumbnail or a customized category icon.
- **Product Information:** Item name, category tag (Electronics, Clothing, Home & Living, Automotive, Personal Care, Other), and purchase cost.
- **Smart Countdown Badge (Dynamic Color-Coded):**
  - **Green / Accent:** Secure status with more than 30 days remaining.
  - **Orange:** Attention needed; less than 30 days remaining.
  - **Red Alert:** Critical window (< 3 days). On the final day, a live countdown (hours, minutes, seconds) activates.
  - **Crimson / Dark Red:** Expired warranties.
- **Quick Interactions:** A single tap opens the detailed view (full-resolution receipts, serial number, barcode, warranty conditions). A long press toggles batch selection.

---

## 6. Floating Action Button (FAB)

The expanding `+` button in the lower-right corner allows you to quickly log new items:

- **Manual Entry:** A comprehensive step-by-step form to input product details, purchase date, standard warranty, extended warranty, return window, serial numbers, receipt photos, and PDF files.
- **Receipt Enhancer (Fiş Kurtarıcı):** A specialized photo restoration tool with image filters to crop, sharpen, and restore fading thermal paper receipts.
- **Scroll to Top:** A floating shortcut that appears whenever you scroll down, returning you to the top of the list in one click.

---

## 7. Floating Modern Bottom Navigation Bar

Effortlessly switch between core sections using the sleek, floating bottom navigation bar:

- **Warranties (Home):** Your central inventory vault and active warranty dashboard.
- **Analytics:** Spending distribution, category statistics, and an interactive monthly entries line chart.
- **Tools:** QR/Barcode scanner, peer-to-peer warranty transfer, video inventory walk, and trash bin.
- **Settings:** Accent colors, currency selector, notifications, and encrypted `.vcb` backup/restore via Android SAF.

---

## 8. Support & Feedback

If you encounter an issue, have a feature suggestion, or wish to report a bug:

- Open the app and navigate to **Settings > About > Report Bug & Feedback**.
- Feedback submitted through the in-app form is securely delivered directly to the development team.
- You can also reach the developer through the verified Google Play Store listing.
- *To protect against spam crawlers and automated bots, email addresses are intentionally not published in plain text.*
