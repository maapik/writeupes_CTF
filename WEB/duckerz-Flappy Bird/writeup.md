# Flappy Bird - Duckerz CTF 
**Category**: Web  

## Solution
1. Открыл консоль (F12).
2. Ввёл: `UI.score.curr = 1000000`.
3. Вызвал: `getFlag()`.
4. т.к по отдельности если введем `UI.score.curr = 1000000` то `getFlag()` не вызовится и нам не дадут флаг(было у меня так до переигровки),

поэтому я сделал сразу два вызова:

`UI.score.curr = 1000000;
getFlag();`

## Подробное объяснение + скрины:
задача:

![1](https://github.com/maapik/writeupes_CTF/blob/main/WEB/duckerz-Flappy%20Bird/1.png)

![2](https://github.com/maapik/writeupes_CTF/blob/main/WEB/duckerz-Flappy%20Bird/2.png)

открываем инструменты разраба Ф12 и заходим в источники в JS скрипт тут есть функция `getFlag()`:

![3](https://github.com/maapik/writeupes_CTF/blob/main/WEB/duckerz-Flappy%20Bird/3.png)

далее мы находим score он находится в разделе UI:

![4](https://github.com/maapik/writeupes_CTF/blob/main/WEB/duckerz-Flappy%20Bird/4.png)

короче я перепроходил еще раз и у меня получилось прописать раздельно `UI.score.curr = 1000000` и `getFlag()` вам возможно придется прописать шаг 4 который выше
тут я показываю раздельно:
после смерти в игре у нас score 0 в игре показывается и best 0 мы не перезагружаем игру
открываем консоль и вызываем score curr т.к это у нас ветвь скажем так в JS то она вызывается через точки и через UI итог:`UI.score.curr = 1000000`:


![5](https://github.com/maapik/writeupes_CTF/blob/main/WEB/duckerz-Flappy%20Bird/5.png)

теперь у нас score = 1000000
далее вызываем getFlag() и вуаля у нас есть флаг:

![6](https://github.com/maapik/writeupes_CTF/blob/main/WEB/duckerz-Flappy%20Bird/7.png)

