# Duckerz: Скрытая документация
**Категория:** Web Enumeration (Dirbusting)  
**Уровень:** Easy 

---

## Описание
> *"Хорошая документация – залог понятного и безопасного кода"*

Но документация **спрятана** — нужно найти.

---

## Решение (3 команды)

```bash
# 1. Запуск gobuster
gobuster dir -u --- -w --- 

# 2. Найдено:
/docs (200 OK)

# 3. Переход: http://duckerz.local/docs
# Внизу страницы:
#   "Документация разработчика: /administrator_secret_folder/creds.txt"

# 4. Переход: http://duckerz.local/administrator_secret_folder/creds.txt
