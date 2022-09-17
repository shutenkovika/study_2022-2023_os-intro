---
# Front matter
title: "Отчёт по лабораторной работе №2"
subtitle: "Дискреционное
разграничение прав в Linux. Основные
атрибуты
"
author: "Виктория Михайловна Шутенко"

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
  name: el
### Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text

---

# Цель работы

Приобрести практические навыки в работы в консоли с атрибутами файлов, закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.

# Ход работы 

1. В установленной при выполнении предыдущей лабораторной работы операционной системе создала учётную запись пользователя guest (использую учётную запись администратора):

```useradd guest```  

2. Задала пароль для пользователя guest (использую учётную запись администратора):

```passwd guest```

![Cоздание пользователя guest.](images/image1.png){ #fig:001 width=70% }

3. Вошла в систему от имени пользователя guest.

![Авторизация пользователя guest.](images/image2.png){ #fig:001 width=70% }

4. Определила директорию, в которой я находитесь, командой pwd. Сравнила её с приглашением командной строки. Она не является моей домашней директорией, зашла в домашнюю директорию.

5. Уточнила имя моего пользователя командой:

 ```whoami```

6. Уточнила имя моего пользователя, его группу, а также группы, куда входит пользователь, командой:

 ```id```  
 
 Выведенные значения uid, gid и др. запомнила. Сравнила вывод id с выводом команды groups. Они одинаковые.

7. Сравнила полученную информацию об имени пользователя с данными, выводимыми в приглашении командной строки.

8. Просмотрела файл /etc/passwd командой

```cat /etc/passwd```

Нашла в нём свою учётную запись. Определила uid пользователя. Определила gid пользователя. Сравнила найденные значения с полученными в предыдущих пунктах.

![Определение директори, команда id. Просмотр файла](images/image3.png){ #fig:001 width=70% }

![Просмотр файла.](images/image4.png){ #fig:001 width=70% }

9.  Определила существующие в системе директории командой

```ls -l /home/```

10. Проверила, какие расширенные атрибуты установлены на поддиректориях, находящихся в директории /home, командой:


```lsattr /home```


11. Создала в домашней директории поддиректорию dir1 командой

```mkdir dir1```

![Определение существующей директории, поиск расширенных атрибутов, создание dir1.](images/image5.png){ #fig:001 width=70% }

Определила  командами ls -l и lsattr, какие права доступа и расширенные атрибуты были выставлены на директорию dir1.

12. Сняла с директории dir1 все атрибуты командой

```chmod 000 dir1```
и проверила с её помощью правильность выполнения команды

```ls -l```

13. Попыталась создать в директории dir1 файл file1 командой

```echo "test" > /home/guest/dir1/file1```

![Снятие атрибутов, создание файла file1.](images/image6.png){ #fig:001 width=70% }

14. Заполнила таблицу «Установленные права и разрешённые действия»
(см. табл. 2.1), выполняя действия от имени владельца директории (файлов), определив опытным путём, какие операции разрешены, а какие нет.
Если операция разрешена, занесите в таблицу знак «+», если не разрешена, знак «-».

|Права директории|Права ф|Создание ф|Удаление ф|Запись в ф|Чтение ф|Смена директории|Просмотр файлов в директории|Переименование ф|Смена атриб|
| d(000)         |  000  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    -      |
| d(000)         |  100  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    -      |
| d(000)         |  200  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    -      |
| d(000)         |  300  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    -      |
| d(000)         |  400  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    -      |
| d(000)         |  500  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    -      |
| d(000)         |  600  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    -      |
| d(000)         |  700  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    -      |
| d(100)         |  000  |    -     |    -     |    -     |   -    |     +          |         -                  |       -        |    +      |
| d(100)         |  100  |    -     |    -     |    -     |   -    |     +          |         -                  |       -        |    +      |
| d(100)         |  200  |    -     |    -     |    +     |   -    |     +          |         -                  |       -        |    +      |
| d(100)         |  300  |    -     |    -     |    +     |   -    |     +          |         -                  |       -        |    +      |
| d(100)         |  400  |    -     |    -     |    -     |   +    |     +          |         -                  |       -        |    +      |
| d(100)         |  500  |    -     |    -     |    -     |   +    |     +          |         -                  |       -        |    +      |
| d(100)         |  600  |    -     |    -     |    +     |   +    |     +          |         -                  |       -        |    +      |
| d(100)         |  700  |    -     |    -     |    +     |   +    |     +          |         -                  |       -        |    +      |
| d(200)         |  000  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(200)         |  100  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(200)         |  200  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(200)         |  300  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(200)         |  400  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(200)         |  500  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(200)         |  600  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(200)         |  700  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(300)         |  000  |    +     |    +     |    -     |   -    |     +          |         -                  |       -        |    +      |
| d(300)         |  100  |    +     |    +     |    -     |   -    |     +          |         -                  |       -        |    +      |
| d(300)         |  200  |    +     |    +     |    -     |   -    |     +          |         -                  |       -        |    +      |
| d(300)         |  300  |    +     |    +     |    +     |   -    |     +          |         -                  |       -        |    +      |
| d(300)         |  400  |    +     |    +     |    +     |   +    |     +          |         -                  |       -        |    +      |
| d(300)         |  500  |    +     |    +     |    +     |   +    |     +          |         -                  |       -        |    +      |
| d(300)         |  600  |    +     |    +     |    +     |   +    |     +          |         -                  |       -        |    +      |
| d(300)         |  700  |    +     |    +     |    +     |   +    |     +          |         -                  |       -        |    +      |
| d(400)         |  000  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(400)         |  100  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(400)         |  200  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(400)         |  300  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(400)         |  400  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(400)         |  500  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(400)         |  600  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(400)         |  700  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(500)         |  000  |    -     |    -     |    -     |   -    |     +          |         +                  |       -        |    +      |
| d(500)         |  100  |    -     |    -     |    -     |   -    |     +          |         +                  |       -        |    +      |
| d(500)         |  200  |    -     |    -     |    -     |   -    |     +          |         +                  |       -        |    +      |
| d(500)         |  300  |    -     |    -     |    +     |   -    |     +          |         +                  |       -        |    +      |
| d(500)         |  400  |    -     |    -     |    +     |   +    |     +          |         +                  |       -        |    +      |
| d(500)         |  500  |    -     |    -     |    +     |   +    |     +          |         +                  |       -        |    +      ||
| d(500)         |  600  |    -     |    -     |    +     |   +    |     +          |         +                  |       -        |    +      |
| d(500)         |  700  |    -     |    -     |    +     |   +    |     +          |         +                  |       -        |    +      |
| d(600)         |  000  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(600)         |  100  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(600)         |  200  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(600)         |  300  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(600)         |  400  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(600)         |  500  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(600)         |  600  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(600)         |  700  |    -     |    -     |    -     |   -    |     -          |         -                  |       -        |    +      |
| d(700)         |  000  |    +     |    +     |    -     |   -    |     +          |         -                  |       -        |    +      |
| d(700)         |  100  |    +     |    +     |    -     |   -    |     +          |         -                  |       +        |    +      |
| d(700)         |  200  |    +     |    +     |    -     |   -    |     +          |         -                  |       +        |    +      |
| d(700)         |  300  |    +     |    +     |    +     |   -    |     +          |         -                  |       +        |    +      |
| d(700)         |  400  |    +     |    +     |    +     |   +    |     +          |         -                  |       +        |    +      |
| d(700)         |  500  |    +     |    +     |    +     |   +    |     +          |         -                  |       +        |    +      |
| d(700)         |  600  |    +     |    +     |    +     |   +    |     +          |         +                  |       +        |    +      |
| d(700)         |  700  |    +     |    +     |    +     |   +    |     +          |         +                  |       +        |    +      |

# Библиография{.unnumbered}

1. Зегжда Д. П., Ивашко А. М. Основы безопасности информационных систем. — М.: Горячая линия — Телеком, 2016. — 452 с.
2. Мэйволд Э. Безопасность сетей. Эком, 2016 г., 528 с. — http://www.intuit.ru/department/security/netsec/


::: {#refs}
:::



