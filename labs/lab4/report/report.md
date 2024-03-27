---
## Front matter
title: "Лабораторная работа № 4"
subtitle: "Дискреционное разграничение прав в Linux. Расширенные атрибуты"
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

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

# Выполнение лабораторной работы

1. От имени пользователя guest определили расширенные атрибуты файла
/home/guest/dir1/file1 командой lsattr /home/guest/dir1/file1
Установили командой chmod 600 file1 на файл file1 права, разрешающие чтение и запись для владельца файла. Попробовали установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest: chattr +a /home/guest/dir1/file1
В ответ получили отказ от выполнения операции.

![chattr +a](image/41.png){#fig:001 width=90%}

2. Зашли на третью консоль с правами администратора. Попробовали установить расширенный атрибут на файл /home/guest/dir1/file1 от имени суперпользователя: chattr +a /home/guest/dir1/file1

![третья консоль](image/42.png){#fig:002 width=90%}

3. От пользователя guest проверели правильность установления атрибута:
lsattr /home/guest/dir1/file1
Выполнили дозапись в файл file1 слова «test» командой echo "test" /home/guest/dir1/file1
После этого выполнили чтение файла file1 командой cat /home/guest/dir1/file1
Убедились, что слово test было успешно записано в file1.
Попробовали удалить файл file1, либо стереть имеющуюся в нём информацию командой
echo "abcd" > /home/guest/dirl/file1
Попробовали переименовать файл. Попробовали с помощью команды chmod 000 file1 установить на файл file1 права, например, запрещающие чтение и запись для владельца файла. 

![chmod 000 file1](image/43.png){#fig:003 width=90%}

4. Сняли расширенный атрибут a с файла /home/guest/dirl/file1 от имени суперпользователя командой
chattr -a /home/guest/dir1/file1

![chattr -a ](image/44.png){#fig:004 width=90%}

5. Повторили операции, которые ранее не удавалось выполнить. 

![echo "test" ](image/45.png){#fig:005 width=90%}

6. Операция chattr +i. 

![chattr +i](image/46.png){#fig:006 width=90%}

7. Повторили действия по шагам, заменив атрибут «a» атрибутом «i».

![chmod 000](image/47.png){#fig:007 width=90%}

# Выводы

В ходе выполнения данной лабораторной работы были получены практические навыки работы в консоли с расширенными атрибутами файлов. В результате выполнения работы повысили свои навыки использования интерфейса командой строки (CLI), познакомились на примерах с тем, как используются основные и расширенные атрибуты при разграничении доступа. Имели возможность связать теорию дискреционного разделения доступа (дискреционная политика безопасности) с её реализацией на практике в ОС Linux. Составили наглядные таблицы, поясняющие какие операции возможны при тех или иных установленных правах. Опробовали действие на практике расширенных атрибутов «а» и «i». 

# Список литературы{.unnumbered}

::: {#refs}
:::
