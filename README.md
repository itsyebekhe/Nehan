# 🛡️ Nehan (نهان) | Secure Client-Side Pastebin

![Version](https://img.shields.io/badge/version-3.0.0-blue)
![Security](https://img.shields.io/badge/Security-AES--256-green)
![Platform](https://img.shields.io/badge/Platform-PWA%20%7C%20Web-orange)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

**Nehan** is a secure, serverless, and offline-capable text sharing tool designed for maximum privacy and stability.

It uses **Client-Side Encryption** to lock your text on your device using your personal password *before* sending it to the server. This means neither the storage provider (PasteHub) nor the proxy service can ever read your data.

🔗 **Live Demo:** [https://itsyebekhe.github.io/Nehan/](https://itsyebekhe.github.io/Nehan/)

---

## 🇮🇷 فارسی (Persian)

**نهان** ابزاری برای اشتراک‌گذاری امن متن است که با تمرکز بر حفظ حریم خصوصی و پایداری اینترنت طراحی شده است.

این برنامه متن‌های شما را **درون مرورگر (گوشی یا کامپیوتر)** و با استفاده از رمزنگاری AES-256 قفل می‌کند و سپس نسخه قفل‌شده را به سرور می‌فرستد. این یعنی هیچ‌کس (حتی سرور یا واسطه‌ها) بدون داشتن «کلید شخصی» شما، قادر به خواندن متن نیست.

### ✨ ویژگی‌ها
*   🔒 **رمزنگاری سمت کاربر:** متن قبل از خروج از گوشی شما رمز می‌شود.
*   📱 **وب‌اپلیکیشن (PWA):** قابلیت نصب روی گوشی (iOS و Android) و کارکرد مشابه اپلیکیشن بومی.
*   📡 **پایداری بالا:** استفاده از پروکسی برای عبور از محدودیت‌های مرورگر (CORS) و اتصال به سرورهای داخلی.
*   🎨 **رابط کاربری مدرن:** پشتیبانی از حالت تاریک (Dark Mode) و فونت وزیرمتن.
*   🔑 **مدیریت کلید:** ذخیره کلید رمزنگاری در حافظه مرورگر برای سهولت استفاده.

### 📲 راهنمای نصب (PWA)
برای دسترسی همیشگی و تمام صفحه، نهان را به صفحه اصلی گوشی خود اضافه کنید:

1.  **آیفون (iOS):** در سافاری دکمه Share را بزنید و گزینه **Add to Home Screen** را انتخاب کنید.
2.  **اندروید (Android):** در کروم منوی سه نقطه را بزنید و گزینه **Install App** یا **Add to Home Screen** را انتخاب کنید.

---

## 🇬🇧 English Description

### 🚀 Key Features
*   **Zero-Knowledge Architecture:** The server only stores encrypted gibberish. You hold the decryption key.
*   **Serverless & Static:** Runs entirely as a static HTML file. No backend code required on your host.
*   **Offline Capable:** All assets (CryptoJS, Fonts, CSS) are local. The app interface loads even without internet.
*   **CORS Bypass:** Integrated with `corsproxy.io` to allow seamless communication with the backend storage from GitHub Pages.
*   **Persisted Settings:** Remembers your Dark/Light theme preference and Secret Key.

### 🛠️ Technology Stack
*   **Frontend:** HTML5, CSS3 (Embedded SVG Icons), Vanilla JavaScript.
*   **Encryption:** [CryptoJS](https://github.com/brix/crypto-js) (AES-256).
*   **Storage Backend:** [PasteHub.ir](https://pastehub.ir) (Used as a dumb storage).
*   **Font:** Vazirmatn (Local WOFF2).

### 📖 How it Works

1.  **Encryption:** When you click "Send", the app takes your text and your "Secret Key". It uses `CryptoJS.AES.encrypt` to turn the text into ciphertext.
2.  **Upload:** The app sends *only* the ciphertext to PasteHub via a CORS Proxy.
3.  **Retrieval:** When downloading, the app fetches the ciphertext.
4.  **Decryption:** The app uses the key stored in your browser to decrypt the text locally and display it.

### 📦 Installation (Self-Hosting)

1.  Clone the repository:
    ```bash
    git clone https://github.com/itsyebekhe/Nehan.git
    ```
2.  Navigate to the folder:
    ```bash
    cd Nehan
    ```
3.  Serve the file locally or upload to GitHub Pages.
    *   *Note:* Ensure the `assets` folder contains `crypto-js.min.js` and `Vazirmatn.woff2`.

### ⚠️ Security Notice
*   **Proxy Traffic:** Traffic is routed through `corsproxy.io` to bypass browser restrictions on GitHub Pages. Since payload is encrypted **before** transmission, the proxy cannot read your data.
*   **Key Safety:** If you lose your "Secret Key", your data is lost forever. There is no password recovery.

### 📄 License
Distributed under the MIT License. See `LICENSE` for more information.

---
*Designed with ❤️ for Privacy.*
