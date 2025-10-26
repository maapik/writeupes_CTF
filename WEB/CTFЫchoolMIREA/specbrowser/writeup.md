# AdminBrowser - [CTF, даркнет-страница] 
**Категория**: Web (User-Agent Bypass)  

## Описание
Страница в даркнете открывается только с "специальным браузером" (adminbrowser). Обычный браузер показывает "To render this page, you need to use adminbrowser". 

Название сайта — подсказка, но его не найти в обычном интернете.

## Решение
1. Открыл DevTools (F12) → "Network" и обновил страницу, чтобы увидеть запрос.
2. Проверил ответ сервера — код 200, но контент фильтруется по User-Agent.
3. Изменил User-Agent в DevTools → "Network conditions" → "User agent" → "Custom" → ввёл "adminbrowser" (или "Mozilla/5.0 (AdminBrowser)").
4. Обновил страницу — сервер принял User-Agent, и показался флаг (или скрытый контент с флагом).

