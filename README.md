# TelegramInfoBot

<p align="center">
  <b>Production-ready Telegram bot for employee directory from Excel</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8%2B-blue" />
  <img src="https://img.shields.io/badge/aiogram-3.x-blueviolet" />
  <img src="https://img.shields.io/badge/aiogram--dialog-enabled-success" />
  <img src="https://img.shields.io/badge/systemd-ready-green" />
  <img src="https://img.shields.io/badge/status-v1.1.0%20stable-brightgreen" />
</p>

---

## Описание

**🚀 TelegramCoorporateManager** — Корпоративный Telegram-бот для сотрудников компании на Python 3.8 
Справочник сотрудников, структура компании, дни рождения, админ-панель, доступ по whitelist групп и тем.

Бот подходит для компаний, где нужно быстро находить сотрудников по фамилии, отделу или ФИО, получать контактные данные, отправлять поздравления с днём рождения и ограничивать доступ только разрешённым группам, каналам и сотрудникам.

Данные берутся из Excel-файла, который может быть размещён:

- на Google Drive / Google Sheets;
- на любом файловом хостинге;
- по прямой ссылке на `.xlsx`.

---

# ✨ Возможности

## 👥 Сотрудники
- Каталог сотрудников из Excel
- Карточки сотрудников
- Фильтрация по компаниям → отделам → сотрудникам
- Поиск сотрудников *(в личном чате)*
- Дни рождения на ближайшие 7 дней

---

## 🏢 Наша структура
- Компании
- Отделы
- Сотрудники по подразделениям

---

## 🔐 Контроль доступа
Доступ имеют только:

✅ Администраторы  
✅ Участники разрешенной группы/канала  
✅ Разрешённые темы (topics whitelist)

Поддерживается:

- whitelist чатов  
- whitelist тем  
- автоматический выход из неразрешённых групп  
- отдельные разрешённые темы для поздравлений

---

## 🖼 Кастомные изображения
Отдельные изображения для:

- Главное приветствие
- Компании
- Отделы
- Сотрудники

Поддержка:

- JPG
- PNG
- Дефолтные изображения внутри проекта

---

## ⚙ Админ панель
Через Telegram:

- Управление названием компании
- Описание компании
- Изображения
- Администраторы
- Чаты / Каналы
- Темы
- Excel источник
- Перезапуск бота

---

## 🎂 Авто поздравления
Автоматически в 09:00

```text
Сегодня день рождения у сотрудника:
Иванов Иван Иванович
```

Timezone:

```text
Asia/Yekaterinburg (GMT+5)
```

---

# 🧠 Диалоговый интерфейс
Полностью на:

- aiogram 3
- aiogram-dialog

Навигация:

```text
⬅ Назад
❌ Отмена
```

- Всё работает в одном сообщении  
- Нет дублей окон  
- Автовозврат в главное меню через 15 секунд

---

# 🧹 Автоочистка
Удаляются через 30 секунд:

- служебные сообщения
- пользовательские сообщения в разрешённой теме

Не удаляется:

- главное приветственное сообщение

---

# 📊 Excel структура

Таблица:

| Колонка | Значение |
|--------|----------|
| A | ФИО |
| B | Должность |
| C | Отдел |
| D | Телефон |
| E | E-mail |
| F | День рождения |
| G | Компания |

Поддерживаются:

- Google Sheets
- XLSX
- прямые ссылки

Регистр игнорируется:

```text
IT == it == It
```

---

# 🛠 Стек

```txt
aiogram==3.4.1
aiohttp==3.9.5
APScheduler==3.10.4
numpy==1.24.4
pandas==1.5.3
openpyxl==3.1.2
python-dotenv==1.0.1
pydantic==2.5.3
pydantic-settings==2.2.1
pytz==2024.1
Pillow==10.4.0
aiogram-dialog==2.1.0
```

---

# 🚀 Установка

```bash
unzip TelegramCoorporateManager.zip
cd TelegramCoorporateManager
sudo bash install.sh
```

Установщик спросит:

```text
- Bot Token
- Admin ID
- Company name
- Description
- Image URL
- Excel URL
- Allowed Group ID
```

---

## ▶ Запуск

```bash
sudo systemctl start telegramcorporatemanager
```

Статус:

```bash
sudo systemctl status telegramcorporatemanager
```

Логи:

```bash
sudo journalctl -u telegramcorporatemanager -f
```

---

## ❌ Удаление

```bash
sudo bash /opt/TelegramCoorporateManager/uninstall.sh
```

Остановит:

- сервис
- процессы
- удалит папку проекта

---

# 📂 Структура проекта

```bash
app/
assets/
 └── defaults/
config/
data/
install.sh
uninstall.sh
README.md
```

---

# 🛡 Автовосстановление
Если бот падает:

```ini
Restart=always
RestartSec=5
```

systemd автоматически перезапускает.

---

# 🔮 Roadmap
- LDAP/AD интеграция
- SSO
- HR модули
- Органиграмма
- PDF экспорт сотрудников
- REST API

---

# 🤝 Автор

**Andrey K.**  
GitHub: https://github.com/ander1k

---

## ⭐ Если проект полезен — поставьте Star
