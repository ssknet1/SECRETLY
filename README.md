# SECRETLY — Telegram Mini App

## Что это?
Полноценное мобильное приложение внутри Telegram. Клиенты открывают его прямо в чате — никаких установок, никаких App Store.

## Функционал
- 🏠 Главная — логотип, акции, быстрые действия
- 👕 Каталог — 8 товаров с фильтрами и поиском
- 📦 Заявки — история заказов с чатом
- 👤 Профиль — данные пользователя из Telegram

## Как подключить к Telegram боту

### 1. Создай бота
Напиши @BotFather в Telegram:
```
/newbot
```
Дай имя: `SECRETLY Shop`
Дай username: `secretlyshop_bot`

### 2. Получи токен
BotFather даст токен вида: `1234567890:ABC...`

### 3. Загрузи файл на хостинг
Загрузи `index.html` на любой хостинг с HTTPS:
- GitHub Pages (бесплатно)
- Vercel (бесплатно)
- Timeweb / Beget
- Любой VPS

URL должен быть вида: `https://secretly.ru/app/`

### 4. Создай кнопку в боте
Напиши @BotFather:
```
/setmenubutton
```
Выбери бота → укажи URL приложения → название кнопки: `Открыть магазин`

### 5. Или через команду в боте
В коде бота добавь:
```python
from telegram import WebAppInfo, KeyboardButton, ReplyKeyboardMarkup

button = KeyboardButton("🛍 Открыть SECRETLY", web_app=WebAppInfo(url="https://secretly.ru/app/"))
markup = ReplyKeyboardMarkup([[button]])
await update.message.reply_text("Добро пожаловать!", reply_markup=markup)
```

## Локальный тест
Просто открой `index.html` в браузере — работает и без Telegram.
Данные хранятся в localStorage.

## Деплой на GitHub Pages (бесплатно)
1. Создай репозиторий на github.com
2. Загрузи `index.html`
3. Settings → Pages → Source: main branch
4. URL будет: `https://ВАШ_НИК.github.io/secretly-app/`

## Структура
```
index.html   — всё приложение в одном файле
README.md    — эта инструкция
```
