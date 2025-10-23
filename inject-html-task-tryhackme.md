---
# yaml-language-server: $schema=schemas\page.schema.json
Object type:
    - Page
Creation date: "2025-10-23T17:29:35Z"
Created by:
    - maapik
id: bafyreidfiibdsf7oybh5pd7td7oeqqrzkcnoacxxpxn47k2z3qfax262d4
---
# inject HTML task tryhackme   
есть таск:   
![Screenshot 2025-10-23 201356](files\screenshot-2025-10-23-201356.png)    
Решение: открываем этот сайт и видим данную картину:   
![Screenshot 2025-10-23 201456](files\screenshot-2025-10-23-201456.png)    
   

введя в поле *whats your name?* условно loh мы получим welcome loh уяснили   
т.к это таск внутри tryhackme а не внешний сайт , я могу посмотреть код элемента фрейма т.е один из двух окнов при нажатии просмотреть код фрейма мы увидим это:   
![Screenshot 2025-10-23 201650](files\screenshot-2025-10-23-201650.png)    
   

мы знаем что нам нужно обмануть  поле ввода, тут скорее всего должна стоять защита на xss запрос, а защита стоит в JS скрипте и тут есть ссылка на него при переходе мы увидим это:   
![Screenshot 2025-10-23 201826](files\screenshot-2025-10-23-201826.png)    
и тут у нас открывается дорога на 2 варианта решения задачи:   
**1 самый простой**:
мы видим строчку с условием ввода анти xss система скажем так:   
![Screenshot 2025-10-23 201923](files\screenshot-2025-10-23-201923.png)    
в конце написано:
`alert('Congratulations! The answer is ' + decodeBase64("SFRNTF9JTkozQ1RJME4="))`   
мы можем декодировать то что находится в скобках у decodeBase64 в cyberchef и получить флаг   
**2 способ как просит задача:**
видя условие этого кода мы можем сделать вывод что мы можем встроить ссылку в имя где пишется welcome (….) через html инъекцию, благодаря данному нам условию итог выглядит так:   
`<a href="http://hacker.com">loh</a>`   
ввожу это в строку ввода и нам выведет флаг
Ч.Т.Д   
