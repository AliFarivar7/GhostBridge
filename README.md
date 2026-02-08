# GhostBridge
# 👻 GhostBridge - تانل امن و پروکسی منیجر هوشمند (نسخه ۴)

**گوست‌بریج (GhostBridge)** یک ابزار قدرتمند و فوق‌سبک برای عبور از فیلترینگ شدید است. این ابزار با استفاده از پروتکل اختصاصی `Stealth XOR` ترافیک شما را کاملاً مخفی کرده و بین سرور ایران و خارج تانل می‌زند.

## ✨ ویژگی‌های کلیدی
- **هوشمند:** تشخیص خودکار سرور ایران/خارج و پیشنهاد تنظیمات مناسب.
- **مخفی (Stealth):** استفاده از مکانیزم Handshake + رمزنگاری چرخشی. اگر کسی غیر از سرور خودتان به پورت وصل شود، کانکشن قطع می‌شود (Anti-Probe).
- **همه کاره:** مدیریت تانل، نصب MTProto تلگرام و Socks5 فقط با یک دستور.
- **کم مصرف:** نوشته شده با زبان Go، بدون سربار اضافی TLS.
- **بدون قطعی:** سرویس خودکار (Systemd) که در صورت ریستارت سرور، تانل را بالا می‌آورد.

## 🚀 نصب و راه‌اندازی سریع

دستور زیر را در ترمینال سرور (هم ایران و هم خارج) کپی کنید:
```bash
wget -O setup.sh https://raw.githubusercontent.com/USERNAME/REPO/main/setup.sh && chmod +x setup.sh && ./setup.sh
*(لینک بالا را با آدرس گیت‌هاب خود جایگزین کنید)*

---

## 📖 راهنمای گام‌به‌گام

### 1️⃣ سرور خارج (Foreign)
1. منو را باز کنید (`ghost`).
2. اگر پروکسی تلگرام می‌خواهید، گزینه **3** (MTProto) را بزنید و نصب کنید. پورت و سکرت را یادداشت کنید.
3. برای ساخت تانل، گزینه **2** را بزنید.
- نقش **Server (2)** را انتخاب کنید.
- یک **پسورد تانل** دلخواه وارد کنید (مثلاً `MySecret123`).
- پورت تانل (مثلاً `9999`) و پورت هدف (مثلاً پورت MTProto که ساختی `443`) را وارد کنید.

### 2️⃣ سرور ایران (Iran)
1. منو را باز کنید.
2. گزینه **2** (Configure Tunnel) را بزنید.
- نقش **Client (1)** را انتخاب کنید.
- **پسورد تانل** را دقیقاً مشابه سرور خارج وارد کنید (`MySecret123`).
- آی‌پی سرور خارج را وارد کنید.
- پورت لوکال (مثلاً `443`) و پورت ریموت تانل (`9999`) را وارد کنید.

### 🎉 تمام!
حالا در تلگرام، پروکسی را با **IP ایران** و پورت **443** تنظیم کنید. سرعت باورنکردنی خواهد بود!

---
**تذکر:** این ابزار برای استفاده شخصی و دور زدن تحریم‌ها طراحی شده است.


### 3. فایل README.md (انگلیسی)

```markdown
# 👻 GhostBridge - Stealth Tunnel & Proxy Manager V4

**GhostBridge** is a high-performance, obfuscated TCP tunneling tool designed to bypass deep packet inspection (DPI) and censorship. It utilizes a custom handshake protocol to remain invisible to active probing.

## 🔥 Key Features
- **Smart Detection:** Auto-detects server location (IR/EU) and suggests roles.
- **Stealth Protocol:** Uses Rolling XOR + Auth Handshake. Unauthorized connections are silently dropped.
- **Multi-Tool:** Built-in installer for MTProto Proxy (Telegram) and SOCKS5 (Dante).
- **Lightweight:** Written in Go, compiles to a single binary. No heavy TLS overhead.
- **Auto-Persist:** Runs as a systemd service automatically.

## 📥 Installation

Run this one-liner on both servers:
```bash
wget -O setup.sh https://raw.githubusercontent.com/USERNAME/REPO/main/setup.sh && chmod +x setup.sh && ./setup.sh

## ⚙️ Quick Start Guide

### Step 1: Foreign Server (The Source)
1. Run `ghost`.
2. **Optional:** Install MTProto (Option 3) or SOCKS5 (Option 4). Note the ports.
3. Select **Option 2** to configure the tunnel.
- Role: **Server (2)**.
- Set a **Tunnel Password**.
- Map a Tunnel Port (e.g., `8080`) to your Local Service Port (e.g., `443`).

### Step 2: Iran Server (The Bridge)
1. Run `ghost`.
2. Select **Option 2**.
- Role: **Client (1)**.
- Enter the **same Tunnel Password**.
- Enter Foreign Server IP.
- Map Local Port (e.g., `443`) to Remote Tunnel Port (`8080`).

### Step 3: Enjoy
Connect your clients to the **Iran Server IP**. The traffic is securely tunneled to the foreign server.

---
*Open Source & Free*


### روش آپلود در GitHub (خیلی ساده)

1.  در کامپیوتر خودت یک پوشه بساز.
2.  فایل `setup.sh` (کد بالا) و دو تا فایل `README.md` (یا یکی ترکیبی) رو توش ذخیره کن.
3.  برو توی سایت GitHub.com و لاگین کن.
4.  دکمه **New Repository** (سبز رنگ) رو بزن.
5.  اسم بذار (مثلاً `GhostBridge`) و **Public** رو انتخاب کن. Create رو بزن.
6.  توی صفحه بعدی، لینک "uploading an existing file" رو پیدا کن و کلیک کن.
7.  فایل `setup.sh` و `README.md` رو بکش بنداز اونجا.
8.  دکمه **Commit changes** رو بزن.
9.  تمام! حالا روی فایل `setup.sh` توی گیت‌هاب کلیک کن، دکمه **Raw** رو بزن و لینک آدرس بار رو کپی کن. این همون لینکیه که باید جلوی `wget` بذاری.
