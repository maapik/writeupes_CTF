inject HTML task tryhackme
есть таск:

![screenshot](https://github.com/maapik/writeupes_CTF/blob/main/HTML_inject/1.png)

Решение: открываем этот сайт и видим данную картину:
![2](https://github.com/maapik/writeupes_CTF/blob/main/HTML_inject/2.png)


введя в поле whats your name? условно loh мы получим welcome loh уяснили
т.к это таск внутри tryhackme а не внешний сайт ,
я могу посмотреть код элемента фрейма т.е один из двух окнов при нажатии "просмотреть код фрейма" мы увидим это:
![3](https://github.com/maapik/writeupes_CTF/blob/main/HTML_inject/3.png)

мы знаем что нам нужно обмануть  поле ввода, тут скорее всего должна стоять защита по типу на xss запрос 
а защита стоит в JS скрипте и тут есть ссылка на него 
при переходе мы увидим это:
![4](https://github.com/maapik/writeupes_CTF/blob/main/HTML_inject/4.png)
и тут у нас открывается дорога на 2 варианта решения задачи
1 самый простой:
мы видим строчку с условием ввода анти xss система скажем так:
![5](https://github.com/maapik/writeupes_CTF/blob/main/HTML_inject/5.png)
в конце написано:
alert('Congratulations! The answer is ' + decodeBase64("SFRNTF9JTkozQ1RJME4="))
мы можем просто декодировать то что находится в скобках у decodeBase64 в cyberchef и получить флаг
2 способ как просит задача:
видя условие этого кода мы можем сделать вывод что мы можем встроить ссылку в имя где пишется welcome (….) через html инъекцию 
 итог выглядит так:
 "<a href="http://hacker.com">loh</a>"
 ввожу это в строку ввода и нам выведет флаг
 ![6](https://github.com/maapik/writeupes_CTF/blob/main/HTML_inject/6.png)
Ч.Т.Д
