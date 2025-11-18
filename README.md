# آموزش کامل ساخت ربات تلگرام با پایتون ۱۴۰۴ - از صفر تا ربات ۲۴ ساعته حرفه‌ای (pyTelegramBotAPI)

<p align="center">
  <img src="[https://raw.githubusercontent.com/theesmaeil1/.github/main/assets/telegram-bot-python-bot-banner.png](https://fiverr-res.cloudinary.com/images/q_auto,f_auto/gigs/207441761/original/aaf3c0f3c869463f18b04ff9c8d547f261e04445/make-a-telegram-bot-using-python.png)" alt="Telegram Bot Python Banner" width="100%"/>
</p>

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Telebot](https://img.shields.io/badge/pyTelegramBotAPI-Latest-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
![Stars](https://img.shields.io/github/stars/theesmaeil1/telegram-bot-tutorial?style=social)

**آموزش ۱۰۰٪ رایگان، فارسی، قدم به قدم و فوق‌العاده ساده برای ساخت اولین ربات تلگرام با پایتون**  
مناسب برای مبتدی‌ها | بدون نیاز به دانش قبلی | اجرا روی ویندوز و سرور ۲۴ ساعته

---

### این آموزش رو theesmaeil1 نوشته و به‌روزرسانی کرده
همه جا منو با همین آیدی پیدا می‌کنی ↓

[![GitHub](https://img.shields.io/badge/GitHub-theesmaeil1-000000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/theesmaeil1)
[![YouTube](https://img.shields.io/badge/YouTube-theesmaeil1-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtube.com/@theesmaeil1)
[![Instagram](https://img.shields.io/badge/Instagram-theesmaeil1-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/theesmaeil1)
[![Telegram](https://img.shields.io/badge/Telegram-theesmaeil1-0088CC?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/theesmaeil1)
[![Discord](https://img.shields.io/badge/Discord-theesmaeil1-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/users/theesmaeil1)

---

## فهرست مطالب
- [چرا این آموزش بهترینه؟](#چرا-این-آموزش-بهترینه)
- [چی یاد می‌گیری؟](#چی-یاد-می‌گیری)
- [پیش‌نیازها](#پیشنیازها)
- [ساخت ربات در تلگرام (دریافت توکن)](#ساخت-ربات-در-تلگرام)
- [نصب کتابخانه‌ها](#نصب-کتابخانهها)
- [ساختار پروژه](#ساختار-پروژه)
- [توضیح خط به خط کد](#توضیح-خط-به-خط-کد)
- [کد کامل bot.py](#کد-کامل-botpy)
- [فایل .env (امنیت توکن)](#فایل-env)
- [اجرا روی ویندوز](#اجرا-روی-ویندوز)
- [اجرا روی VPS یا سرور لینوکس (۲۴ ساعته)](#اجرا-روی-vps-۲۴-ساعته)
- [نکات پیشرفته و امنیت](#نکات-پیشرفته-و-امنیت)
- [سوالات متداول](#سوالات-متداول)

---

### چرا این آموزش بهترینه؟
- کاملاً به زبان فارسی و ساده
- توضیح خط به خط (حتی مبتدی‌ها می‌فهمن)
- استفاده از `.env` برای امنیت توکن (نه گذاشتن توکن در کد!)
- دکمه‌های زیبا + اکو + خوش‌آمدگویی شخصی‌سازی شده
- آموزش اجرا روی کامپیوتر شخصی و سرور واقعی
- آماده برای ویدیو آموزشی و قرار دادن در رزومه

---

### چی یاد می‌گیری؟
- ساخت ربات با BotFather  
- کار با `pyTelegramBotAPI` (telebot)  
- دکمه‌های زیر صفحه‌کلید (ReplyKeyboard)  
- خوش‌آمدگویی با اسم کاربر  
- امنیت توکن با `python-dotenv`  
- اجرای ۲۴ ساعته روی سرور  
- پروژه آماده برای گیت‌هاب و یوتیوب

---

### پیش‌نیازها
- ویندوز، لینوکس یا مک
- پایتون ۳.۹ یا بالاتر ([دانلود پایتون](https://python.org))
- یک حساب تلگرام

---

### ساخت ربات در تلگرام (۲ دقیقه)
1. به `@BotFather` پیام بده  
2. `/newbot` رو بفرست  
3. اسم ربات رو بنویس  
4. یوزرنیم با `bot` تموم بشه (مثال: `mybot_by_theesmaeil1_bot`)  
5. توکن رو کپی کن → **هرگز تو گیت‌هاب عمومی نذار!**

---

### نصب کتابخانه‌ها
```bash
pip install pyTelegramBotAPI python-dotenv
```

---

### ساختار پروژه
```
Telegram-Bot-Tutorial/
├── bot.py
├── .env              ← توکن اینجا
├── .gitignore        ← داخلش بنویس: .env
├── requirements.txt  ← اختیاری
└── README.md         ← همین فایل
```

---

### توضیح خط به خط کد (خیلی مهم!)

```python
import telebot                              # کتابخانه اصلی ربات
from telebot.types import ReplyKeyboardMarkup, KeyboardButton  # برای دکمه
from dotenv import load_dotenv              # امنیت توکن
import os                                   # دسترسی به متغیرهای محیطی

load_dotenv()                               # فایل .env رو لود کن
TOKEN = os.getenv("BOT_TOKEN")              # توکن رو از فایل امن بگیر
bot = telebot.TeleBot(TOKEN)                # ساخت ربات

# تابع ساخت منوی اصلی
def main_menu():
    markup = ReplyKeyboardMarkup(resize_keyboard=True, row_width=2)
    btn1 = KeyboardButton("دکمه ۱")
    btn2 = KeyboardButton("دکمه ۲")
    btn3 = KeyboardButton("درباره ربات")
    btn4 = KeyboardButton("خداحافظ")
    markup.add(btn1, btn2, btn3, btn4)
    return markup

# دستور /start
@bot.message_handler(commands=['start'])
def start(message):
    name = message.from_user.first_name
    text = f"سلام {name} جان! به ربات حرفه‌ای من خوش اومدی!\nیکی از دکمه‌ها رو بزن یا هر چی دوست داری بنویس"
    bot.send_message(message.chat.id, text, reply_markup=main_menu())

# دکمه‌ها
@bot.message_handler(func=lambda m: m.text == "دکمه ۱")
def btn1(m): bot.reply_to(m, "عالی زدی دکمه ۱ رو!")

@bot.message_handler(func=lambda m: m.text == "دکمه ۲")
def btn2(m): bot.reply_to(m, "دکمه ۲ هم خیلی خفنه!")

@bot.message_handler(func=lambda m: m.text == "درباره ربات")
def about(m):
    bot.reply_to(m, "ساخته شده توسط @theesmaeil1 با پایتون و pyTelegramBotAPI\nسال ۱۴۰۴ - کاملاً رایگان")

@bot.message_handler(func=lambda m: m.text == "خداحافظ")
def bye(m): bot.reply_to(m, "موفق باشی! زود برگرد")

# اکو برای بقیه پیام‌ها
@bot.message_handler(func=lambda m: True)
def echo(m):
    bot.reply_to(m, f"تو نوشتی:\n{m.text}")

# شروع ربات
print("ربات توسط theesmaeil1 روشن شد!")
bot.infinity_polling()
```

---

### کد کامل bot.py (کپی کن و استفاده کن)

```python
import telebot
from telebot.types import ReplyKeyboardMarkup, KeyboardButton
from dotenv import load_dotenv
import os

load_dotenv()
TOKEN = os.getenv("BOT_TOKEN")
bot = telebot.TeleBot(TOKEN)

def main_menu():
    markup = ReplyKeyboardMarkup(resize_keyboard=True, row_width=2)
    markup.add("دکمه ۱", "دکمه ۲", "درباره ربات", "خداحافظ")
    return markup

@bot.message_handler(commands=['start'])
def start(message):
    name = message.from_user.first_name
    bot.send_message(message.chat.id,
                     f"سلام {name} عزیز!\nبه ربات من خوش اومدی!\nدکمه‌ها رو بزن یا هر چی دلت خواست بنویس",
                     reply_markup=main_menu())

@bot.message_handler(func=lambda m: m.text == "دکمه ۱")
def btn1(m): bot.reply_to(m, "دکمه ۱ خیلی خوبه!")

@bot.message_handler(func=lambda m: m.text == "دکمه ۲")
def btn2(m): bot.reply_to(m, "دکمه ۲ هم عالیه!")

@bot.message_handler(func=lambda m: m.text == "درباره ربات")
def about(m):
    bot.reply_to(m, "ساخته شده توسط @theesmaeil1\npyTelegramBotAPI + python-dotenv\nکاملاً رایگان و متن‌باز")

@bot.message_handler(func=lambda m: m.text == "خداحافظ")
def bye(m): bot.reply_to(m, "بای بای! موفق باشی")

@bot.message_handler(func=lambda m: True)
def echo(m):
    bot.reply_to(m, f"تو نوشتی:\n{m.text}")

print("ربات توسط @theesmaeil1 با موفقیت اجرا شد!")
bot.infinity_polling()
```

### فایل .env (حتماً بساز!)
```
BOT_TOKEN=7123456789:AAH...توکن_واقعی_خودت_اینجا...
```

### اجرا روی ویندوز
```bash
python bot.py
```

### اجرا روی VPS یا سرور لینوکس (۲۴ ساعته با screen)
```bash
sudo apt update && sudo apt install screen python3-pip -y
pip install pyTelegramBotAPI python-dotenv
screen -S mybot
python3 bot.py
# Ctrl+A بعد D → ربات همیشه روشن می‌مونه!
```

---

### نکات پیشرفته و امنیت
- هرگز توکن رو مستقیم در کد نذار
- فایل `.env` رو به `.gitignore` اضافه کن
- از `screen` یا `pm2` یا `systemd` برای ۲۴ ساعته ماندن استفاده کن
- بعداً می‌تونی دکمه اینلاین، پرداخت، دیتابیس و ... اضافه کنی

---

### سوالات متداول
**سوال:** ربات کار نمی‌کنه؟  
**جواب:** توکن درست باشه + پایتون نصب باشه + اینترنت وصل باشه

**سوال:** چطور ۲۴ ساعته روشن بمونه؟  
**جواب:** از VPS + screen یا Replit یا Railway یا Render استفاده کن

---

حالا وقتشه پروژه‌تو بسازی، ویدیو بگیری و به همه نشون بدی که چقدر حرفه‌ای شدی!  
لینک این ریپازیتوری رو به دوستات بده، استار یادت نره!

موفق باشی قهرمان!  
ساخته شده با ❤️ توسط **@theesmaeil1** — سال ۱۴۰۴

#ربات_تلگرام #پایتون #آموزش_پایتون #pyTelegramBotAPI #برنامه_نویسی #ربات_ساز_تلگرام
