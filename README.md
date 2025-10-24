# 🌍 Radio dal Mondo - Telegram Mini App

Mini-app Telegram per ascoltare radio da tutto il mondo.

## 🚀 Demo Live

**URL della mini-app:** https://radio-mondo-telegram.vercel.app/

## 📱 Come usare su Telegram

Per integrare questa mini-app in Telegram, hai bisogno di un bot. Ecco come fare:

### 1. Crea un bot su Telegram

1. Apri Telegram e cerca [@BotFather](https://t.me/BotFather)
2. Invia il comando `/newbot`
3. Segui le istruzioni per creare il tuo bot
4. Salva il **token** che ricevi

### 2. Codice Python per il bot

Installa le librerie necessarie:

```bash
pip install python-telegram-bot
```

Crea un file `bot.py` con questo codice:

```python
from telegram import Update, WebAppInfo, InlineKeyboardMarkup, InlineKeyboardButton
from telegram.ext import Application, CommandHandler, ContextTypes

WEBAPP_URL = "https://radio-mondo-telegram.vercel.app"

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    kb = [
        [InlineKeyboardButton("🎧 Apri Mini-App Radio", web_app=WebAppInfo(url=WEBAPP_URL))]
    ]
    await update.message.reply_text(
        "Benvenuto! Clicca sul pulsante per ascoltare radio dal mondo direttamente su Telegram 👇",
        reply_markup=InlineKeyboardMarkup(kb)
    )

application = Application.builder().token("IL_TUO_TOKEN_BOT").build()
application.add_handler(CommandHandler("start", start))
application.run_polling()
```

### 3. Avvia il bot

```bash
python bot.py
```

### 4. Usa il bot

1. Cerca il tuo bot su Telegram
2. Invia il comando `/start`
3. Clicca sul pulsante "🎧 Apri Mini-App Radio"
4. La mini-app si aprirà direttamente in Telegram!

## 🎵 Radio disponibili

- BBC World Service (UK)
- RSI Rete Uno (Svizzera)
- Rai Radio 1 (Italia)
- NPR News (USA)
- Studio Brussel (Belgio)
- Radio 3 (Spagna)
- Radio Paradise
- K-Pop (Korea)
- The Beatles Channel
- Radio Rock (Italy)

## 🛠️ Tecnologie usate

- HTML5 + JavaScript
- Telegram Web Apps SDK
- Vercel (hosting)
- GitHub (repository)

## 📝 Licenza

Progetto open source - sentiti libero di usarlo e modificarlo!

---

**Creato con ❤️ per Telegram**
