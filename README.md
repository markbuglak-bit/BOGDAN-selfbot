# Telegram Selfbot

Простой селф-бот на Python для пересылки/копирования сообщений из одного или нескольких каналов в указанный канал назначения.

## Что делает
- читает сообщения из каналов, указанных в `SOURCE_CHANNELS`
- пересылает или копирует их в `DESTINATION_CHANNEL`
- сохраняет состояние: `last_ids.json`, `message_map.json`, `stats.json`, `keywords.json`
- проверяет конфигурацию перед запуском через `check.py`
- управляется через `run.bat`

## Структура проекта
- `selfbot.py` — основной Telegram selfbot на Telethon
- `bot.py` — модуль управления ботом/настройками
- `config_loader.py` — загрузка и нормализация конфигурации
- `check.py` — проверка синтаксиса Python и валидность `config.json`
- `requirements_bot.txt` — зависимости проекта
- `run.bat` — меню запуска и проверка конфигурации
- `run_hidden.bat` — скрытый запуск для автозапуска
- `config.json` — настройки бота и данные доступа Telegram

## Установка
1. Установите Python 3.11+ или совместимую версию.
2. Перейдите в папку проекта:
   ```bat
   cd /d "d:\bogdan\Bot BOGDAN\Bot MAIN"
   ```
3. Установите зависимости:
   ```bat
   python -m pip install -r requirements_bot.txt
   ```

## Настройка
1. Откройте `config.json`.
2. Задайте свои значения:
   - `API_ID` и `API_HASH` — данные Telegram API
   - `SESSION_NAME` — имя сессии Telethon
   - `SOURCE_CHANNELS` — каналы для чтения
   - `DESTINATION_CHANNEL` — канал назначения
   - `BOT_TOKEN`, `ALLOWED_USERS`, `BLOCKED_USERS` — опционально для управления
3. Проверьте, что все обязательные параметры указаны и валидны.

## Запуск
- Через меню:
  ```bat
  run.bat
  ```
- Прямой запуск:
  ```bat
  python selfbot.py
  ```

## Проверка
Перед запуском выполните:
```bat
python check.py
```

## Рекомендации
- `config.json` содержит секретные данные. Не публикуйте его в открытых репозиториях.
- Сессия Telethon хранится в `selfbot.session`.
- Для скрытого автозапуска используйте `run_hidden.bat`.

## Удалённые временные файлы
- `check_syntax.py` — неактивный тестовый файл
- `selfbot.session` и `selfbot.session-journal` — временные файлы сессии Telegram
- папка `__pycache__` — скомпилированные Python-байткоды
