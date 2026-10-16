# Aippy Bot 🤖

بات هوش مصنوعی دیسکورد — چت + ساخت عکس، کاملاً **رایگان** روی Cloudflare Workers (پلن رایگان، ۲۴/۷).

**ساختهٔ تیم توسعه‌دهندگان Aippy** ✨

[![Deploy to Cloudflare](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/izad369/aippy-bot)

---

## امکانات

| کامند | کار | هزینه |
|---|---|---|
| `/ask` | چت با هوش مصنوعی (فارسی/انگلیسی) | رایگان — Workers AI |
| `/image` | ساخت عکس با Flux (1:1، 2:3، 3:2) | رایگان + پشتیبان Pollinations |
| `/help` | راهنما | — |

## نصب (۳ دقیقه)

1. دکمه **Deploy to Cloudflare** بالا را بزن و مراحل را تأیید کن.
2. در داشبورد Cloudflare وارد وورکر `aippy-bot` شو → **Settings → Variables and Secrets** و این سه را اضافه کن:
   - `DISCORD_APP_ID` ← Application ID از [Discord Developer Portal](https://discord.com/developers/applications)
   - `DISCORD_PUBLIC_KEY` ← Public Key از تب Bot
   - `DISCORD_BOT_TOKEN` ← توکن بات (نوع: Secret)
3. در همان پورتال دیسکورد، تب Bot → **Interactions Endpoint URL** را بگذار:
   `https://aippy-bot.<yoursubdomain>.workers.dev/interactions`
4. در مرورگر باز کن: `https://aippy-bot.<yoursubdomain>.workers.dev/setup`
   → باید ببینی: `✅ Commands registered`
5. تمام! برو دیسکورد و `/ask` یا `/image` بزن 🎉

> **نکته:** بات آنلاین (سبز) نمایش داده نمی‌شود ولی همیشه جواب می‌دهد — معماری بدون اتصال دائمی = رایگان و بی‌دردسر.

## استقرار دستی (بدون دکمه Deploy)

- `worker.js` را در ادیتور وورکر کلادفلر پیست کن (Workers & Pages → Create Worker → Edit code)
- `wrangler.toml` از قبل binding هوش مصنوعی (`AI`) را تعریف کرده است
- بعد قدم‌های ۲ تا ۵ بالا

## فایل‌ها

- `worker.js` — کل منطق بات (تک‌فایل، بدون وابستگی)
- `wrangler.toml` — تنظیمات Cloudflare (اسم وورکر + Workers AI binding)
