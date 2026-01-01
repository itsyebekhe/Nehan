# 🛡️ Nehan (نهان) | Secure Client-Side Pastebin

![Version](https://img.shields.io/badge/version-3.1.0-blue)
![Security](https://img.shields.io/badge/Security-AES--256-green)
![Platform](https://img.shields.io/badge/Platform-PWA%20%7C%20Local%20Server-orange)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

**Nehan** is a secure, open-source text sharing tool designed for maximum privacy and stability. It features a modern **Glassmorphism** design and supports multiple deployment methods.

It uses **Client-Side Encryption** to lock your text on your device using your personal password *before* sending it to the server. This means neither the storage provider (PasteHub) nor the proxy service can ever read your data.

🔗 **Live Demo:** [https://itsyebekhe.github.io/Nehan/](https://itsyebekhe.github.io/Nehan/)

---

## 🇮🇷 فارسی (Persian)

### «نهان» چیست؟
**نهان (Nehan)** یک سامانه متن‌باز برای اشتراک‌گذاری امن متن و اطلاعات حساس است. هدف اصلی این پروژه، ایجاد راهکاری ساده، زیبا و کاملاً امن برای انتقال داده‌ها بدون نگرانی از خوانده شدن آن‌ها توسط سرورها یا ابزارهای تحلیلی است.

این برنامه بر اساس معماری **Zero-Knowledge (عدم آگاهی سرور)** طراحی شده است. این یعنی متن شما پیش از خروج از مرورگر، در دستگاه شما رمزگذاری می‌شود و سرورهای ذخیره‌سازی (PasteHub) تنها یک رشته کاراکترهای نامفهوم (Ciphertext) را دریافت می‌کنند. بدون داشتن «کلید رمزنگاری» شخصی شما، هیچ‌کس در جهان قادر به باز کردن قفل متن نخواهد بود.

### ✨ ویژگی‌های برجسته

1.  **🔒 امنیت در سطح کلاینت:**
    *   تمامی فرآیند رمزگذاری با الگوریتم قدرتمند **AES-256** و توسط کتابخانه `CryptoJS` مستقیماً در مرورگر کاربر انجام می‌شود.
    *   سرور تنها نقش یک انبار ساده را بازی می‌کند و هیچ اطلاعاتی از محتوای پیام شما ندارد.

2.  **🎨 طراحی بصری مدرن (Glassmorphism):**
    *   رابط کاربری جدید با طراحی شیشه‌ای (Glassmorphism) و پس‌زمینه‌های شفاف و متحرک.
    *   انیمیشن‌های نرم (Smooth Animations) برای ارائه تجربه‌ای روان و حرفه‌ای.
    *   پشتیبانی کامل از حالت تاریک (Dark Mode) و روشن (Light Mode) با تطبیق خودکار با سیستم عامل.

3.  **📱 وب‌اپلیکیشن (PWA) و مولتی‌پلتفرم:**
    *   قابلیت نصب روی گوشی‌های آیفون و اندروید به عنوان یک اپلیکیشن بومی (Native App Experience).
    *   سازگاری کامل با **تلگرام مینی‌اپ (WebApp)** برای استفاده مستقیم از داخل چت تلگرام.

4.  **🖥️ پشتیبانی از سرور محلی (Local Server):**
    *   اگر می‌خواهید امنیت را دوچندان کنید، می‌توانید برنامه را روی کامپیوتر شخصی یا گوشی اندروید خود اجرا کنید.
    *   در این حالت، نیاز به هیچ پروکسی عمومی (مانند corsproxy.io) نخواهید داشت و ارتباط با سرور ذخیره‌سازی از طریق لوکال هاست شما برقرار می‌شود.
    *   قابلیت اجرا روی اندروید با استفاده از **Termux** بدون نیاز به روت کردن گوشی.

5.  **🔑 مدیریت هوشمند کلید:**
    *   امکان تولید کلیدهای تصادفی و ذخیره آن‌ها در حافظه مرورگر (LocalStorage) برای سهولت استفاده.
    *   اگرچه پیشنهاد می‌شود برای امنیت بیشتر، کلید را در جایی امن یادداشت کنید.

### 📋 معماری امنیتی (چگونه کار می‌کند؟)

مراحل ارسال پیام در نهان به شرح زیر است:

1.  **ورود داده:** شما متن محرمانه خود و یک "کلید شخصی" وارد می‌کنید.
2.  **رمزگذاری (Local):** برنامه با استفاده از کلید شما، متن را به یک کد طولانی و نامفهوم تبدیل می‌کند. این عمل در داخل مرورگر شما اتفاق می‌افتد.
3.  **انتقال:** کد رمز شده به سرور PasteHub ارسال می‌شود.
4.  **ذخیره:** سرور این کد را نگه می‌دارد. چون این کد با کلید شما قفل شده است، حتی ادمین PasteHub نمی‌تواند محتوا را بخواند.
5.  **بازگشایی:** گیرنده کد را می‌گیرد، کلید شخصی را وارد می‌کند و در مرورگر خود، متن اصلی را باز می‌کند.

---

### 🚀 راهنمای نصب و اجرا

شما می‌توانید نهان را به دو روش استفاده کنید:

#### روش ۱: استفاده از نسخه وب (PWA) - ساده‌ترین راه
این روش برای کاربران عادی که دسترسی به سرور ندارند مناسب است. از یک پروکسی عمومی برای عبور از محدودیت‌های شبکه استفاده می‌شود.

1.  **در آیفون (iOS):**
    *   سایت را در مرورگر **Safari** باز کنید.
    *   روی دکمه **Share** (مربع و فلش به بالا) کلیک کنید.
    *   گزینه **Add to Home Screen** را انتخاب کنید.
2.  **در اندروید (Android):**
    *   سایت را در مرورگر **Chrome** باز کنید.
    *   منوی سه نقطه (⋮) را بزنید.
    *   گزینه **Install App** یا **Add to Home Screen** را بزنید.

#### روش ۲: اجرای سرور محلی (Local Server) - پیشنهادی برای پیشرفته‌ها
با این روش، برنامه روی دستگاه خود شما به عنوان سرور اجرا می‌شود. این روش نیازی به پروکسی خارجی ندارد و برای محیط‌های اینترانتی یا مواقعی که اینترنت ناپایدار است بسیار عالی عمل می‌کند.

##### الف) اجرا روی کامپیوتر (Windows / Mac / Linux)

1.  نصب برنامه **Node.js** از وب‌سایت رسمی (نسخه ۱۸ یا جدیدتر ترجیح داده می‌شود).
2.  فایل‌های پروژه (`index.html` و `server.js`) را در یک پوشه قرار دهید.
3.  ترمینال (CMD یا PowerShell یا Terminal) را باز کنید و به پوشه پروژه بروید:
    ```bash
    cd path/to/Nehan
    ```
4.  دستور زیر را اجرا کنید:
    ```bash
    node server.js
    ```
5.  مرورگر خود را باز کنید و به آدرس `http://localhost:3000` بروید.

##### ب) اجرا روی اندروید (با استفاده از Termux)

با این قابلیت، می‌توانید یک وب‌سایت امن را روی گوشی خود میزبانی کنید (مثل داشتن هاست شخصی).

1.  اپلیکیشن **Termux** را از F-Droid یا Play Store نصب کنید.
2.  برنامه Termux را باز و دستورات زیر را وارد کنید:
    ```bash
    pkg update && pkg upgrade
    pkg install nodejs
    ```
3.  یک پوشه بسازید و فایل‌های `server.js` و `index.html` را درون آن کپی کنید (یا با ابزارهای مدیریت فایل Termux آن را ایجاد کنید).
4.  دستور اجرای سرور را وارد کنید:
    ```bash
    node server.js
    ```
5.  اکنون مرورگر کروم گوشی خود را باز کنید و به آدرس `http://localhost:3000` بروید.

---

## 🇬🇧 English Description

### 🚀 Key Features
*   **Zero-Knowledge Architecture:** The server only stores encrypted gibberish. You hold the decryption key.
*   **Modern UI/UX:** Beautiful Glassmorphism design with smooth animations and native Dark Mode support.
*   **Hybrid Deployment:** 
    *   **Static Mode:** Runs purely as an HTML file on GitHub Pages (uses CORS proxy).
    *   **Local Server Mode:** Run your own backend (Node.js) on PC/Android for zero external dependencies.
*   **Offline Capable:** PWA capable, allowing to interface to load without internet.
*   **Persisted Settings:** Remembers your Theme preference and Secret Key.

### 🛠️ Technology Stack
*   **Frontend:** HTML5, CSS3 (Glassmorphism + Animations), Vanilla JavaScript.
*   **Backend (Optional):** Node.js (Native HTTP/HTTPS) for local proxying.
*   **Encryption:** [CryptoJS](https://github.com/brix/crypto-js) (AES-256).
*   **Storage Backend:** [PasteHub.ir](https://pastehub.ir) (Used as a dumb storage).
*   **Font:** Vazirmatn.

### 📖 How it Works

1.  **Encryption:** When you click "Send", the app takes your text and your "Secret Key". It uses `CryptoJS.AES.encrypt` to turn text into ciphertext locally.
2.  **Upload:**
    *   *GitHub Pages Mode:* App sends ciphertext to `corsproxy.io` -> `PasteHub`.
    *   *Local Server Mode:* App sends ciphertext to your localhost -> `PasteHub`.
3.  **Retrieval:** When downloading, the app fetches ciphertext.
4.  **Decryption:** The app uses the key stored in your browser to decrypt text locally and display it.

### 📦 Installation & Usage

#### Option 1: Web Hosting (GitHub Pages)
1.  Clone the repository.
2.  Upload `index.html` and assets to a static host.
3.  **Note:** This mode uses `corsproxy.io` to bypass browser restrictions. Since data is encrypted **before** transmission, the proxy cannot read it.

#### Option 2: Local Server (Recommended for Privacy)
Run the app on your own machine or Android phone using the included `server.js`.

**For PC (Windows/Mac/Linux):**
1.  Install [Node.js](https://nodejs.org/).
2.  Place `index.html` and `server.js` in the same folder.
3.  Open terminal in that folder and run: `node server.js`.
4.  Open browser to `http://localhost:3000`.

**For Android (Termux):**
1.  Install **Termux**.
2.  Run: `pkg update && pkg install nodejs`.
3.  Create a folder and place `server.js` and `index.html` inside.
4.  Run: `node server.js`.
5.  Open Chrome on Android to `http://localhost:3000`.

### ⚠️ Security Notice
*   **Proxy Traffic:** In Static Mode (GitHub Pages), traffic is routed through `corsproxy.io`. Payloads are encrypted **before** transmission.
*   **Key Safety:** If you lose your "Secret Key", your data is lost forever. There is no password recovery.

### 📄 License
Distributed under the MIT License. See `LICENSE` for more information.

---
*Designed with ❤️ for Privacy & Freedom.*
