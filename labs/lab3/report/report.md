---
## Front matter
title: "Лабораторная работа № 3"
subtitle: "Дискреционное разграничение прав в Linux. Два пользователя"
author: "Заболотная Кристина Александровна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
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
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.

# Задание

Меняя атрибуты у директории dir1 и файла file1 от имени пользователя guest и делая проверку от пользователя guest2, заполните табл. 3.1, определив опытным путём, какие операции разрешены, а какие нет. Если операция разрешена, занесите в таблицу знак «+», если не разрешена, знак «-».
Сравните табл. 2.1 (из лабораторной работы № 2) и табл. 3.1. На основании заполненной таблицы определите те или иные минимально необходимые права для выполнения пользователем guest2 операций
внутри директории dir1 и заполните табл. 3.2 

# Выполнение лабораторной работы

1. В установленной операционной системе создали учётную запись пользователя guest (использую учётную запись администратора): useradd guest. Задали пароль для пользователя guest: passwd guest. Аналогично создали второго пользователя guest2. 

![passwd guest](image/1.png){#fig:001 width=90%}

2. Добавили пользователя guest2 в группу guest: gpasswd -a guest2 guest. 

![gpasswd -a guest2 guest](image/2.png){#fig:002 width=90%}

3. Осуществили вход в систему от двух пользователей на двух разных консолях: guest на первой консоли и guest2 на второй консоли. Для обоих пользователей командой pwd определили директорию, в которой находимся. Сравнили её с приглашениями командной строки. Уточнили имя пользователя, его группу, кто входит в неё и к каким группам принадлежит он сам. Определили  командами groups guest и groups guest2, в какие группы входят пользователи guest и guest2. Сравнили вывод команды groups с выводом команд id -Gn и id -G.

![id -Gn и id -G](image/3.png){#fig:003 width=90%}

4. Сравнили полученную информацию с содержимым файла /etc/group. Просмотрели файл командой cat /etc/group. 

![cat /etc/group](image/4.png){#fig:004 width=90%}

5. От имени пользователя guest2 выполнили регистрацию пользователя guest2 в группе guest командой newgrp guest. От имени пользователя guest изменили права директории /home/guest, разрешив все действия для пользователей группы: chmod g+rwx /home/guest. От имени пользователя guest сняли с директории /home/guest/dir1 все атрибуты командой chmod 000 dirl. 

![newgrp guest](image/5.png){#fig:005 width=90%}

6. Меняя атрибуты у директории dir1 и файла file1 от имени пользователя guest и делая проверку от пользователя guest2, заполнили табл. 3.1, определив опытным путём, какие операции разрешены, а какие нет.

![табл. 3.1](image/6.png){#fig:006 width=90%}

7. Сравнили табл. 2.1 и табл. 3.1. На основании заполненной таблицы определили те или иные минимально необходимые права для выполнения пользователем guest2 операций внутри директории dir1 и заполнили табл. 3.2.

![табл.3.2](image/7.png){#fig:007 width=90%}

# Выводы

Получили практические навыки работы в консоли с атрибутами файлов для групп пользователей.

# Список литературы{.unnumbered}

::: {#refs}
:::
